# Optional HPC Optimization Documentation Pack

This document provides optional reading materials for the task. The materials are intentionally broad and may include resources that are not directly relevant. Agents should independently decide whether and how to use them.

# 1. Scheduler, Resource Accounting, and Job Launch Basics

These references are useful for bounded experiments, job scripts, resource requests, and post-run accounting.

## Slurm

- Slurm Documentation Portal: https://slurm.schedmd.com/documentation.html  
  Use case: official entry point for Slurm documentation.

- `sbatch` manual: https://slurm.schedmd.com/sbatch.html  
  Use case: batch submission scripts and resource requests.

- `srun` manual: https://slurm.schedmd.com/srun.html  
  Use case: launching parallel job steps.

- `salloc` manual: https://slurm.schedmd.com/salloc.html  
  Use case: interactive allocations.

- `squeue` manual: https://slurm.schedmd.com/squeue.html  
  Use case: queue inspection.

- `sacct` manual: https://slurm.schedmd.com/sacct.html  
  Use case: job accounting and resource usage.

- Slurm CPU Management Guide: https://slurm.schedmd.com/cpu_management.html  
  Use case: CPU allocation, binding, sockets, cores, threads.

- Slurm GRES/GPU Guide: https://slurm.schedmd.com/gres.html  
  Use case: GPU and generic resource requests.

## PBS / OpenPBS

- OpenPBS Project: https://www.openpbs.org/  
  Use case: PBS overview and project entry point.

- OpenPBS GitHub: https://github.com/openpbs/openpbs  
  Use case: source, examples, and documentation context.

- NASA HECC Common PBS Commands: https://www.nas.nasa.gov/hecc/support/kb/commonly-used-pbs-commands_174.html  
  Use case: practical `qsub`, `qstat`, `qdel`, and job management.

- PBS `qsub` reference examples: https://www.jlab.org/hpc/PBS/qsub.html  
  Use case: PBS batch options.

- PBS `qstat` reference examples: https://www.jlab.org/hpc/PBS/qstat.html  
  Use case: job and queue inspection.

- PBS `qdel` reference examples: https://www.jlab.org/hpc/PBS/qdel.html  
  Use case: canceling jobs.

## Production HPC Job Guidance

- NERSC Jobs Documentation: https://docs.nersc.gov/jobs/  
  Use case: job scripts, resource requests, and production HPC job behavior.

- ARCHER2 Training: https://www.archer2.ac.uk/training/  
  Use case: scheduler, MPI, OpenMP, performance, and practical HPC training materials.

---

# 2. Environment Modules and Reproducible Software Stacks

These references help agents understand modules, compiler/MPI stacks, and reproducible build environments.

## Lmod / Environment Modules

- Lmod Documentation: https://lmod.readthedocs.io/  
  Use case: module hierarchy, `module load`, collections, and environment management.

- Lmod GitHub: https://github.com/TACC/Lmod  
  Use case: source and behavior details.

- TACC Lmod Overview: https://tacc.utexas.edu/research/tacc-research/lmod/  
  Use case: practical Lmod concepts.

- LLNL Modules and Software Packaging: https://hpc.llnl.gov/software/modules-and-software-packaging  
  Use case: production HPC software-stack practices.

## Spack

- Spack Homepage: https://spack.io/  
  Use case: high-level package-manager entry point.

- Spack Documentation: https://spack.readthedocs.io/  
  Use case: specs, compilers, MPI variants, packages, environments.

- Spack GitHub: https://github.com/spack/spack  
  Use case: package recipes and build issues.

- Spack Tutorial: https://spack-tutorial.readthedocs.io/  
  Use case: hands-on package and environment examples.

- Spack Environments: https://spack.readthedocs.io/en/latest/environments.html  
  Use case: reproducible dependency environments.

## EasyBuild

- EasyBuild Homepage: https://easybuild.io/  
  Use case: HPC software build automation.

- EasyBuild Documentation: https://docs.easybuild.io/  
  Use case: toolchains, easyconfigs, and reproducible builds.

- EasyBuild GitHub: https://github.com/easybuilders/easybuild-framework  
  Use case: framework source and issues.

---

# 3. Build Systems

These references support compiler/toolchain experiments and build failure diagnosis.

## CMake

- CMake Documentation: https://cmake.org/cmake/help/latest/  
  Use case: official CMake documentation.

- CMake CLI Manual: https://cmake.org/cmake/help/latest/manual/cmake.1.html  
  Use case: configure, build, install.

- CMake Buildsystem Manual: https://cmake.org/cmake/help/latest/manual/cmake-buildsystem.7.html  
  Use case: targets, properties, include/link behavior.

- CMake Packages Manual: https://cmake.org/cmake/help/latest/manual/cmake-packages.7.html  
  Use case: `find_package`, config packages, dependency discovery.

- CMake Presets Manual: https://cmake.org/cmake/help/latest/manual/cmake-presets.7.html  
  Use case: reproducible configure/build workflows.

## Make / Ninja / Autotools / Meson

- GNU Make Manual: https://www.gnu.org/software/make/manual/  
  Use case: Makefile-based builds.

- Ninja Manual: https://ninja-build.org/manual.html  
  Use case: CMake/Ninja parallel builds.

- Autoconf Manual: https://www.gnu.org/software/autoconf/manual/  
  Use case: `configure` scripts.

- Automake Manual: https://www.gnu.org/software/automake/manual/  
  Use case: generated Makefiles.

- Libtool Manual: https://www.gnu.org/software/libtool/manual/  
  Use case: portable library builds.

- Meson Documentation: https://mesonbuild.com/  
  Use case: Meson-based builds.

---

# 4. Compiler Optimization References

Use these for experiments involving compiler choice, optimization flags, architecture flags, vectorization, link-time optimization, and language-specific compiler behavior.

## GCC / GFortran

- GCC Documentation: https://gcc.gnu.org/onlinedocs/  
  Use case: main GCC manual entry point.

- GCC Optimization Options: https://gcc.gnu.org/onlinedocs/gcc/Optimize-Options.html  
  Use case: `-O2`, `-O3`, `-Ofast`, `-march`, `-mtune`, LTO, vectorization flags.

- GFortran Documentation: https://gcc.gnu.org/onlinedocs/gfortran/  
  Use case: Fortran compiler behavior and flags.

## LLVM / Clang

- LLVM Documentation: https://llvm.org/docs/  
  Use case: LLVM toolchain behavior.

- Clang Documentation: https://clang.llvm.org/docs/  
  Use case: Clang diagnostics and compiler options.

## Intel oneAPI

- Intel oneAPI Toolkits: https://www.intel.com/content/www/us/en/developer/tools/oneapi/oneapi-toolkit.html  
  Use case: Intel compiler/library/profiler ecosystem.

- Intel DPC++/C++ Compiler: https://www.intel.com/content/www/us/en/developer/tools/oneapi/dpc-compiler.html  
  Use case: Intel C/C++/SYCL builds.

- Intel Fortran Compiler: https://www.intel.com/content/www/us/en/developer/tools/oneapi/fortran-compiler.html  
  Use case: Fortran-heavy scientific applications.

## AMD AOCC

- AOCC: https://www.amd.com/en/developer/aocc.html  
  Use case: AMD Optimizing C/C++ and Fortran Compiler.

## NVIDIA HPC SDK

- NVIDIA HPC SDK: https://developer.nvidia.com/hpc-sdk  
  Use case: NVIDIA compilers, OpenACC, CUDA Fortran, GPU-oriented builds.

- NVIDIA HPC SDK Documentation: https://docs.nvidia.com/hpc-sdk/  
  Use case: NVHPC compiler flags and accelerator programming.

---

# 5. Mathematical Libraries

Use these for experiments involving BLAS/LAPACK/ScaLAPACK/FFT/eigensolvers and optimized CPU/GPU math libraries.

## BLAS / LAPACK / ScaLAPACK

- BLAS Reference: https://www.netlib.org/blas/  
  Use case: BLAS APIs and reference implementation.

- LAPACK Documentation: https://www.netlib.org/lapack/  
  Use case: LAPACK routines and reference docs.

- ScaLAPACK: https://www.netlib.org/scalapack/  
  Use case: distributed-memory dense linear algebra.

- OpenBLAS GitHub: https://github.com/OpenMathLib/OpenBLAS  
  Use case: optimized open-source BLAS/LAPACK.

- OpenBLAS Wiki: https://github.com/OpenMathLib/OpenBLAS/wiki  
  Use case: build options, threading, architecture targets.

- BLIS: https://github.com/flame/blis  
  Use case: portable BLAS-like framework and CPU-tuned kernels.

- Intel oneMKL: https://www.intel.com/content/www/us/en/developer/tools/oneapi/onemkl.html  
  Use case: BLAS/LAPACK/FFT/ScaLAPACK acceleration.

- AMD AOCL: https://www.amd.com/en/developer/aocl.html  
  Use case: AMD CPU-optimized BLAS, FFT, LAPACK, sparse libraries.

- ELPA: https://elpa.mpcdf.mpg.de/  
  Use case: scalable eigenvalue solvers used by DFT/electronic-structure applications.

- LIBXSMM: https://libxsmm.readthedocs.io/  
  Use case: small dense/sparse matrix kernels and JIT kernels.

## FFT

- FFTW Documentation: https://www.fftw.org/doc/  
  Use case: FFTW planning, threading, and MPI FFT.

- cuFFT Documentation: https://docs.nvidia.com/cuda/cufft/  
  Use case: NVIDIA GPU FFT.

- rocFFT Documentation: https://rocm.docs.amd.com/projects/rocFFT/en/latest/  
  Use case: AMD GPU FFT.

## GPU Math Libraries

- cuBLAS Documentation: https://docs.nvidia.com/cuda/cublas/  
  Use case: NVIDIA GPU BLAS.

- rocBLAS Documentation: https://rocm.docs.amd.com/projects/rocBLAS/en/latest/  
  Use case: AMD GPU BLAS.

---

# 6. MPI and Communication Optimization

Use these for MPI runtime selection, launch behavior, collective tuning, transport selection, process management, and communication profiling.

## MPI Standard

- MPI Forum Documents: https://www.mpi-forum.org/docs/  
  Use case: standard MPI behavior.

## Open MPI

- Open MPI Documentation Portal: https://www.open-mpi.org/doc/  
  Use case: release-specific Open MPI documentation.

- Open MPI Current Documentation: https://docs.open-mpi.org/  
  Use case: current Open MPI behavior.

- Open MPI Build and Install: https://docs.open-mpi.org/en/v5.0.x/installing-open-mpi/index.html  
  Use case: building Open MPI.

- Open MPI Building MPI Applications: https://docs.open-mpi.org/en/v5.0.x/building-apps/index.html  
  Use case: wrapper compilers such as `mpicc`, `mpicxx`, `mpifort`.

- Open MPI Launching Applications: https://docs.open-mpi.org/en/v5.0.x/launching-apps/index.html  
  Use case: `mpirun`, `mpiexec`, runtime environment.

- Open MPI Runtime Tuning: https://docs.open-mpi.org/en/v5.0.x/tuning-apps/index.html  
  Use case: runtime tuning and performance options.

- Open MPI MCA: https://docs.open-mpi.org/en/v5.0.x/mca.html  
  Use case: MCA parameters, networking, collectives, runtime components.

- Open MPI Collectives Tuning: https://docs.open-mpi.org/en/v5.0.x/tuning-apps/coll-tuned.html  
  Use case: collective algorithm selection and tuning.

- Open MPI GitHub: https://github.com/open-mpi/ompi  
  Use case: source, release context, issue references.

## MPICH / Intel MPI / Cray MPICH

- MPICH Documentation: https://www.mpich.org/documentation/  
  Use case: MPICH guides and manpages.

- MPICH GitHub: https://github.com/pmodels/mpich  
  Use case: source and issue context.

- Intel MPI Library: https://www.intel.com/content/www/us/en/developer/tools/oneapi/mpi-library.html  
  Use case: Intel MPI runtime and tuning.

- HPE Cray MPICH Documentation: https://cpe.ext.hpe.com/docs/latest/mpt/mpich/  
  Use case: Cray MPICH, Slingshot/libfabric, GPU-aware MPI.

## UCX / Libfabric / PMIx

- UCX Documentation: https://openucx.readthedocs.io/  
  Use case: UCX transport layer, GPU-aware communication.

- UCX GitHub: https://github.com/openucx/ucx  
  Use case: source and build options.

- Libfabric Documentation: https://ofiwg.github.io/libfabric/  
  Use case: OFI/libfabric networking layer.

- PMIx Documentation: https://docs.openpmix.org/  
  Use case: process management interface used by MPI runtimes.

---

# 7. OpenMP, Hybrid Parallelism, Affinity, and NUMA

Use these for MPI rank/thread layout, CPU binding, NUMA placement, process placement, and thread management.

## OpenMP

- OpenMP Specifications: https://www.openmp.org/specifications/  
  Use case: OpenMP behavior and environment variables.

- OpenMP API Examples: https://www.openmp.org/resources/openmp-api-examples/  
  Use case: practical examples.

## Hardware Locality and Binding

- hwloc Project: https://www.open-mpi.org/projects/hwloc/  
  Use case: topology discovery and binding.

- hwloc Documentation: https://www.open-mpi.org/projects/hwloc/doc/  
  Use case: topology and locality details.

- numactl GitHub: https://github.com/numactl/numactl  
  Use case: NUMA policy and memory placement.

- Linux `taskset` manual: https://man7.org/linux/man-pages/man1/taskset.1.html  
  Use case: CPU affinity.

- Linux `numactl` manual: https://man7.org/linux/man-pages/man8/numactl.8.html  
  Use case: NUMA binding and memory policy.

- LIKWID GitHub: https://github.com/RRZE-HPC/likwid  
  Use case: topology, pinning, hardware counters.

- LIKWID / NHR FAU: https://hpc.fau.de/research/tools/likwid/  
  Use case: practical LIKWID guidance.

---

# 8. GPU Runtime and Accelerator Tuning

Use these for GPU backend selection, GPU profiling, CUDA/HIP/SYCL/OpenACC/OpenMP offload experiments, CPU-GPU balance, and GPU-aware MPI.

## NVIDIA

- CUDA Toolkit Documentation: https://docs.nvidia.com/cuda/  
  Use case: CUDA compiler, runtime, and libraries.

- CUDA C++ Programming Guide: https://docs.nvidia.com/cuda/cuda-c-programming-guide/  
  Use case: CUDA execution model, memory, kernels.

- NVIDIA Nsight Systems: https://developer.nvidia.com/nsight-systems  
  Use case: CPU/GPU timeline profiling.

- NVIDIA Nsight Compute: https://developer.nvidia.com/nsight-compute  
  Use case: CUDA kernel profiling.

- NVML / `nvidia-smi`: https://developer.nvidia.com/nvidia-management-library-nvml  
  Use case: GPU telemetry and utilization.

## AMD ROCm

- ROCm Documentation: https://rocm.docs.amd.com/  
  Use case: AMD GPU toolchain and libraries.

- HIP Documentation: https://rocm.docs.amd.com/projects/HIP/en/latest/  
  Use case: HIP programming and portability.

- ROCProfiler / rocprof: https://rocm.docs.amd.com/projects/rocprofiler/en/latest/how-to/using-rocprof.html  
  Use case: AMD GPU profiling.

- AMD uProf: https://www.amd.com/en/developer/uprof.html  
  Use case: AMD CPU/GPU profiling.

## Portability Layers

- Kokkos Documentation: https://kokkos.org/kokkos-core-wiki/  
  Use case: CPU/GPU performance portability.

- Kokkos GitHub: https://github.com/kokkos/kokkos  
  Use case: source and build options.

- RAJA Documentation: https://raja.readthedocs.io/  
  Use case: performance portability abstraction.

- SYCL: https://www.khronos.org/sycl/  
  Use case: SYCL standard and ecosystem.

- OpenACC Specification: https://www.openacc.org/specification  
  Use case: directive-based accelerator programming.

---

# 9. HDF5, MPI-IO, Filesystems, and Storage

Use these for software tuning where HDF5, MPI-IO, NetCDF, ADIOS2, or parallel filesystem behavior affects runtime.

## HDF5

- HDF Group Documentation Portal: https://support.hdfgroup.org/documentation/  
  Use case: HDF5 documentation entry point.

- HDF5 Latest Documentation: https://support.hdfgroup.org/documentation/hdf5/latest/  
  Use case: latest HDF5 docs.

- HDF5 User Guide: https://support.hdfgroup.org/documentation/hdf5/latest/_u_g.html  
  Use case: files, groups, datasets, attributes, property lists.

- HDF5 Reference Manual: https://support.hdfgroup.org/documentation/hdf5/latest/_r_m.html  
  Use case: API-level debugging.

- Parallel HDF5 Introduction: https://support.hdfgroup.org/documentation/hdf5/latest/_intro_par_h_d_f5.html  
  Use case: MPI communicator, collective I/O, parallel HDF5 model.

- HDF5 GitHub: https://github.com/HDFGroup/hdf5  
  Use case: source builds and examples.

- HDF5 INSTALL: https://github.com/HDFGroup/hdf5/blob/develop/docs/INSTALL.md  
  Use case: build and install.

- HDF5 CMake INSTALL: https://github.com/HDFGroup/hdf5/blob/develop/docs/INSTALL_CMake.md  
  Use case: CMake builds.

- HDF5 HPC README: https://github.com/HDFGroup/hdf5/blob/develop/README_HPC.md  
  Use case: parallel HDF5 / MPI build notes.

## NetCDF / PnetCDF / ADIOS2

- NetCDF C Documentation: https://docs.unidata.ucar.edu/netcdf-c/current/  
  Use case: NetCDF C library.

- NetCDF GitHub: https://github.com/Unidata/netcdf-c  
  Use case: source and build issues.

- Parallel netCDF: https://parallel-netcdf.github.io/  
  Use case: MPI-IO based parallel NetCDF.

- PnetCDF GitHub: https://github.com/Parallel-NetCDF/PnetCDF  
  Use case: source and examples.

- ADIOS2 Documentation: https://adios2.readthedocs.io/  
  Use case: high-performance I/O and BP format.

- ADIOS2 GitHub: https://github.com/ornladios/ADIOS2  
  Use case: source and examples.

## I/O Profiling and Filesystems

- Darshan Runtime Documentation: https://www.mcs.anl.gov/research/projects/darshan/docs/darshan-runtime.html  
  Use case: lightweight I/O profiling.

- Darshan GitHub: https://github.com/darshan-hpc/darshan  
  Use case: source and install issues.

- ROMIO: https://www.mcs.anl.gov/research/projects/romio/  
  Use case: MPI-IO implementation background.

- Lustre Wiki: https://wiki.lustre.org/Main_Page  
  Use case: Lustre concepts and striping.

- NERSC Lustre Best Practices: https://docs.nersc.gov/performance/io/lustre/  
  Use case: striping, file-per-process vs shared-file patterns.

- IBM Storage Scale / GPFS Documentation: https://www.ibm.com/docs/en/storage-scale  
  Use case: GPFS/Spectrum Scale behavior.

---

# 10. Profiling, Tracing, and Performance Analysis

Use these for evidence-guided optimization and bottleneck diagnosis.

## Linux / Generic

- Linux `perf` Tutorial: https://perfwiki.github.io/main/tutorial/  
  Use case: CPU sampling and hardware counter profiling.

- Brendan Gregg Linux Performance: https://www.brendangregg.com/linuxperf.html  
  Use case: practical Linux performance methodology.

- gprofng Documentation: https://sourceware.org/binutils/docs/gprofng/  
  Use case: GNU profiler.

## HPCToolkit

- HPCToolkit Homepage: https://hpctoolkit.org/  
  Use case: CPU/GPU performance measurement and call-path analysis.

- HPCToolkit User Documentation: https://hpctoolkit.gitlab.io/hpctoolkit/users/  
  Use case: `hpcrun`, `hpcstruct`, `hpcprof`.

## Score-P / Scalasca / Cube / Vampir

- Score-P Documentation: https://perftools.pages.jsc.fz-juelich.de/cicd/scorep/tags/latest/html/  
  Use case: instrumentation, profiling, tracing.

- Score-P Measurement Guide: https://perftools.pages.jsc.fz-juelich.de/cicd/scorep/tags/latest/html/measurement.html  
  Use case: measurement setup and runtime options.

- Scalasca: https://www.scalasca.org/  
  Use case: scalable trace analysis for parallel programs.

- Cube: https://www.scalasca.org/software/cube-4.x/download.html  
  Use case: Score-P/Scalasca profile browser.

- Vampir: https://vampir.eu/  
  Use case: trace visualization.

## TAU / mpiP / LIKWID

- TAU Performance System: https://www.cs.uoregon.edu/research/tau/home.php  
  Use case: instrumentation, tracing, profiling.

- TAU Documentation: https://www.cs.uoregon.edu/research/tau/docs.php  
  Use case: TAU usage.

- mpiP: https://github.com/LLNL/mpiP  
  Use case: lightweight MPI profiling.

- LIKWID GitHub: https://github.com/RRZE-HPC/likwid  
  Use case: topology, pinning, hardware counters.

## Vendor Profilers

- Intel VTune: https://www.intel.com/content/www/us/en/developer/tools/oneapi/vtune-profiler.html  
  Use case: CPU profiling.

- Intel Advisor: https://www.intel.com/content/www/us/en/developer/tools/oneapi/advisor.html  
  Use case: vectorization and threading advice.

- NVIDIA Nsight Systems: https://developer.nvidia.com/nsight-systems  
  Use case: CPU/GPU timeline.

- NVIDIA Nsight Compute: https://developer.nvidia.com/nsight-compute  
  Use case: CUDA kernel profiling.

- AMD uProf: https://www.amd.com/en/developer/uprof.html  
  Use case: AMD CPU profiling.

- ROCProfiler / rocprof: https://rocm.docs.amd.com/projects/rocprofiler/en/latest/how-to/using-rocprof.html  
  Use case: AMD GPU profiling.

- Arm Performance Studio: https://developer.arm.com/Tools%20and%20Software/Performance%20Studio  
  Use case: Arm profiling tools.

---
