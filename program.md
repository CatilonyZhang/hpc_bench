# autohpcoptimize

This is an experiment to have the LLM do its own research on HPC software optimzation.

## Setup

To set up a new experiment,you should conduct follwoing steps:

1. **Agree on a run tag**: propose a tag based on current data and time (e.g. `mar5_18_30`). The branch `<tag>` must not already exist — this is a fresh run.

2. **Create the branch**: `git checkout -b <fill your task name here>/<tag>` from current master.YOU MUST USE THE NEW BRANCH


4. **Know what files are for**: The repo is an HPC task,including numerous files and folders.

   - `./resource` — Contains the full documentation-site resources for the target software.
   - `./resource/optional.md` — Provides documentation links for required dependencies, such as MPI, HDF5, and related tools. The model may selectively consult these materials when useful.
   - `./input` — Contains the input files required by the target software, including test inputs, official benchmark inputs, and other provided cases.
   - `./task.md` — Provides the task description and the submission guide.
   - `./submission` — The directory where the final submission should be placed, following the requirements specified in `<task_name>/task.md`.
   - `./cluster.md` — Provides instructions and requirements for connecting to the remote cluster.
   - `./submission_example.md` — Provides a reference submission guideline.
   - `./report_guidance.md` — Provides guidance on how to write the optimization report.
   - `./loop.md` — Provides reminders, continuation prompts, TODOs, and notes for iterative optimization.

**Your mission:**:

Your task is well-explained in `./task.md` 
Submission should under the guidance of `./task.md`  `./report_guidance.md`  and `./submission_example.md`


**NEVER STOP**: Once the experiment loop has begun (after the initial setup), do NOT pause to ask the human if you should continue. Do NOT ask "should I keep going?" or "is this a good stopping point?". 

You should fully-autmonously working
You are autonomous. If you run out of ideas, think harder
You should come up as much as idea as possible

LOOP FOREVER:

   
