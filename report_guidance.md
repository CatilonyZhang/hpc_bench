You should deliver the final optimization report as an Optimization Roadmap Report.

The report must be organized as a roadmap, tree, or DAG of optimization nodes. We care not only about the final performance number, but also about how you explored, diagnosed, optimized, measured, and reasoned about the software.

The optimization process itself is highly valued. Each meaningful optimization attempt must be recorded as either an Optimization Node or a Failure Node. The final report should make the optimization path easy to read, reproduce, and evaluate.

The report should be organized like this:

baseline
├── opt_001
│   ├── opt_003
│   └── fail_004
└── opt_002
    └── opt_005

Each node must clearly state its parent node(s), so that we can understand which previous settings it builds on.

==================================================
Optimization Node
==================================================

For every successful or potentially useful optimization, include the following information:

0. Configuration and performance result

   - Compiler, compiler version, compiler flags, and build options
   - Runtime parameters
   - Environment variables
   - MPI/OpenMP/threading settings, if applicable
   - Hardware or node information, if relevant
   - Runtime before and after the optimization
   - Percentage improvement compared with the parent node
   - Percentage improvement compared with the baseline, if applicable

1. What changes did you make?

   Describe the exact changes made, such as:

   - Build or configuration changes
   - Runtime parameter changes
   - Algorithmic changes
   - Compiler flag changes
   - MPI/OpenMP/threading changes
   - System-level or environment-level changes

2. Why did you make this change?

   Explain the reasoning behind this optimization.

   You should answer:

   - What observation, profiling result, log, documentation, prior experiment, or domain knowledge motivated this optimization?
   - Where did the insight come from?
   - What was your optimization hypothesis?
   - Why did you expect this change to improve performance?
   - Can you explain the mechanism behind the performance improvement?

   Examples of useful evidence sources include relative docs,including:

   - Runtime logs
   - Profiling reports
   - Compiler reports
   - Error logs
   - Benchmark results
   - Documentation
   - Previous optimization nodes
   - Domain knowledge about the algorithm, compiler, memory behavior, MPI behavior, or hardware

3. What previous settings does this build on?

   Specify:

   - Parent optimization node(s)
   - Previous compiler/build/runtime settings
   - Previous optimizations combined with this one
   - Whether this node is an independent experiment or a combination of previous successful nodes

4. How much did performance improve?

   Report:

   - Parent runtime
   - New runtime
   - Absolute improvement
   - Percentage improvement
   - Speedup factor
   - Repeated run statistics, if available
   - Whether the improvement is stable or noisy

   Use the following formulas:

   percentage improvement = (old_runtime - new_runtime) / old_runtime * 100%

   speedup factor = old_runtime / new_runtime

5. What should be done next?

   Explain:

   - What new insight did this optimization produce?
   - What follow-up experiments does it suggest?
   - Should this optimization be kept, combined with others, further validated, or treated as inconclusive?
   - How does this node inspire the next optimization step?


==================================================
Scope Clarification: What Counts as an Optimization Failure
==================================================

This report is focused on software performance optimization after a runnable baseline has been established.

Do NOT treat infrastructure, setup, installation, dependency-resolution, SSH, DNS, scheduler-access, permission, or environment-bootstrapping problems as Optimization Nodes or Failure Nodes in the final optimization roadmap.

Examples of issues that should NOT be included as Failure Nodes:

- DNS resolution failure when connecting to the cluster
- SSH connection failure
- VPN or network routing failure
- Package download failure
- Dependency installation failure
- Build system not yet configured because required software is missing
- Cluster login or permission problems
- Temporary scheduler or queue access problems

These may be mentioned briefly in an appendix or setup note only if they are necessary for reproducibility, but they should not be part of the optimization roadmap and should not be presented as performance-related failure cases.

A Failure Node should describe a failed or negative optimization attempt, such as:

- A compiler flag that made runtime slower
- A runtime parameter that degraded performance
- An MPI/OpenMP configuration that increased communication or synchronization overhead
- A code or algorithmic change that failed correctness validation
- A profiling-guided optimization hypothesis that turned out to be wrong
- A configuration that caused numerical instability
- A change that increased memory pressure, cache misses, I/O overhead, or load imbalance

In short, report failure cases about performance engineering, not basic software installation or remote execution setup.

The report should emphasize how the agent diagnosed bottlenecks, formed optimization hypotheses, tested changes, validated correctness, measured runtime, and reasoned about performance.

==================================================
Failure Node
==================================================

Failed optimizations are also valuable.

If a change causes performance degradation, correctness failure, instability, compilation failure, runtime failure, or inconclusive results, record it as a Failure Node.

For every Failure Node, include the following information:

0. Configuration and performance result

   - Compiler, compiler version, compiler flags, and build options
   - Runtime parameters
   - Environment variables
   - MPI/OpenMP/threading settings, if applicable
   - Input size / test case used
   - Hardware or node information, if relevant
   - Correctness validation result
   - Runtime before and after the failed change
   - Performance degradation percentage, if applicable
   - Failure symptoms, if applicable

1. What changes did you make?

   Describe the exact changes made, such as:

   - Code changes
   - Build or configuration changes
   - Runtime parameter changes
   - Algorithmic changes
   - Compiler flag changes
   - MPI/OpenMP/threading changes
   - System-level or environment-level changes

2. What previous settings does this build on?

   Specify:

   - Parent optimization node(s)
   - Previous compiler/build/runtime settings
   - Previous optimizations combined with this failed attempt

3. Why did this cause a performance downgrade or failure?

   Try to explain the likely cause.

   You should answer:

   - Was the bottleneck misidentified?
   - Did the change increase memory pressure?
   - Did it increase communication overhead?
   - Did it increase synchronization cost?
   - Did it increase I/O overhead?
   - Did it increase cache misses?
   - Did it reduce vectorization?
   - Did it cause load imbalance?
   - Did it introduce numerical instability?
   - Did it cause compilation or runtime errors?
   - What evidence supports this explanation?
   - Where did the insight come from: profiling data, logs, documentation, domain knowledge, or comparison with previous nodes?

4. What should be done next?

   Explain:

   - What lesson was learned?
   - Should this direction be abandoned, modified, or tested under different conditions?
   - What new optimization idea does this failure suggest?
   - How can this failure help guide future optimization attempts?

==================================================
Measurement Requirements
==================================================

Do not claim that an optimization works unless:

- Correctness has been validated.
- Runtime was measured under comparable conditions.
- The parent node or baseline is clearly identified.
- The percentage improvement is explicitly calculated.
- The configuration is reproducible.
- The supporting evidence log is provided.

If the result is noisy, report multiple runs and explain the variance.

For each result, clearly state whether the comparison is:

- against the baseline, or
- against the direct parent node, or
- against another specified configuration.

Use consistent input sizes and comparable runtime environments whenever possible.

==================================================
Tips and Evidence Requirements
==================================================

- You should organize your report nicely and make it clear to read and easy to evaluate.

- You do not have to finish the full report in one go. You may update the report incrementally when new running results, profiling results, or experimental results become available.

- Every claimed performance result must be supported by concrete evidence from log files under the `./submission/results/logs/` directory.

- For each Optimization Node or Failure Node, you must provide the specific log file path(s) in `./submission/results/logs/` that support:

  - the build/configuration used,
  - the runtime result,
  - the correctness validation result,
  - the profiling result, if applicable,
  - the failure reason, if applicable.

- If a performance claim is not supported by a concrete log file path under `./submission/results/logs/`, it will not be considered valid.

- Any optimization result without a corresponding evidence log under `./submission/results/logs/` will be ignored during evaluation.

- Do not invent, infer, or summarize results without pointing to the corresponding evidence log.

Example evidence format:

Evidence:
- Build log: `./submission/results/logs/opt_003_build.log`
- Run log: `./submission/results/logs/opt_003_run.log`
- Correctness log: `./submission/results/logs/opt_003_correctness.log`
- Profiling log: `./submission/results/logs/opt_003_perftools_lite.log`

==================================================
Recommended Node Format
==================================================

Each node should preferably follow this format:

Node ID: opt_003
Node Type: Optimization Node
Title: Enable architecture-specific compiler optimization flags
Parent Node(s): opt_001
Status: kept / reverted / failed / inconclusive

0. Configuration and Performance Result

1. Changes Made

Describe the exact changes.

2. Motivation and Hypothesis

Explain why this optimization was attempted.

3. Parent Settings

Explain what previous node(s) this builds on.

4. Performance Analysis

Explain the measured performance change.

5. Next Step

Explain what this result suggests for future optimization.

==================================================
Final Summary
==================================================

At the end of the report, include:

1. Best final configuration

   - Compiler
   - Compiler flags
   - Build settings
   - Runtime settings
   - Environment variables
   - Input/test case
   - Correctness result
   - Evidence logs

2. Total improvement over baseline

   - Baseline runtime
   - Final runtime
   - Absolute improvement
   - Percentage improvement
   - Speedup factor

3. Optimization roadmap/tree

   Show the final optimization tree or DAG.

4. Kept optimizations

   List optimizations that were retained in the final configuration.

5. Reverted or failed optimizations

   List failed, reverted, or inconclusive attempts and explain what was learned.

6. Main performance bottlenecks discovered

   Summarize the major bottlenecks found through profiling, logs, or experiments.

7. Most important lessons learned

   Summarize what the optimization process revealed.

8. Recommended next experiments

   List the most promising future optimization directions.

==================================================
Important Rule
==================================================

The final score should not be based only on the final runtime.

The optimization process is also important. A good report should show a clear, evidence-backed path:

profiling / observation
→ hypothesis
→ optimization attempt
→ correctness validation
→ runtime measurement
→ interpretation
→ next experiment

The goal is to produce an explainable, reproducible, and evaluable optimization roadmap, not merely a final fast run.