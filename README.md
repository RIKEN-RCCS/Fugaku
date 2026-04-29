# Fugaku

This landing page provides an overview of the Supercomputer Fugaku operated by
[RIKEN R-CCS](https://www.r-ccs.riken.jp/en/). It aggregates publicly available
resources, software, and documentation. More detailed materials are available
to approved users through official access programs.

> **What's new (2026-04):** AI/ML workflows on A64FX are getting renewed
> investment. See **[AI / Machine Learning on Fugaku](#-ai--machine-learning-on-fugaku-highlight)**
> below — including **DL4Fugaku · oneDNN**, distributed PyTorch / TensorFlow,
> and the ongoing **ollama-on-A64FX** evaluation.

---

## Table of Contents

- [Overview](#overview)
- [Account / Time Application](#account--time-application)
- [Documentation](#documentation)
- [System Access](#system-access)
- [Software Ecosystem](#software-ecosystem)
- [Containerization](#containerization)
- [Libraries](#libraries)
- [AI / Machine Learning on Fugaku ★](#-ai--machine-learning-on-fugaku-highlight)
- [HPC Applications](#hpc-applications)
- [Datasets](#datasets)
- [Benchmarks](#benchmarks)
- [Hardware](#hardware)
- [Development & Optimization](#development--optimization)
- [Related Projects & Initiatives](#related-projects--initiatives)
- [Citation / Acknowledgment](#citation--acknowledgment)

---

## Overview

Fugaku is a flagship exascale-class supercomputer developed by RIKEN R-CCS in
collaboration with Fujitsu. It is powered by the
[A64FX](https://www.r-ccs.riken.jp/en/) ARM-based processor and is designed for
high-performance computing (HPC), AI workloads, and data-centric science.

- [Architecture overview](https://www.r-ccs.riken.jp/en/fugaku/about/)
- [Performance and benchmarks](https://www.r-ccs.riken.jp/en/fugaku/research/awards/)

---

## Account / Time Application

Access to Fugaku is managed through HPCI:

- [Fee-based Access](https://www.hpci-office.jp/en/using_hpci/proposal_submission_current/fugaku_fee_based)
- [Trial Access](https://www.hpci-office.jp/en/using_hpci/proposal_submission_current/fugaku_trial)
- [Other categories](https://www.hpci-office.jp/en/using_hpci/proposal_submission_current)

### New to Fugaku? — A short, opinionated guide

If this is your first attempt at obtaining a Fugaku account, the practical
sequence is roughly as follows:

1. **Check eligibility.** Most academic / industry users in Japan apply via
   the HPCI proposal system. Foreign users may also apply via HPCI; commercial
   use is supported under the fee-based programs.
2. **Pick a category.**
   - *Trial use*  — short-duration, lightweight, recommended for first-time
     evaluation, porting, and benchmarking.
   - *Fee-based use* — production-grade, longer-duration, charges per node-hour.
   - *Open-call (general)* — competitive scientific proposals; review-based.
3. **Get an HPCI ID.** All access goes through HPCI federated authentication.
   Register at the [HPCI Operating Office](https://www.hpci-office.jp/) before
   submitting a proposal.
4. **Submit a proposal** through the HPCI portal. ARiSE / JST AI for Science
   PIs may attach the relevant project number.
5. **After approval:** read the
   [User Guides (R-CCS)](https://www.r-ccs.riken.jp/en/fugaku/user-manuals/),
   then register SSH keys, set up the
   [Spack](https://github.com/RIKEN-RCCS/spack) environment, and submit your
   first job.

> **Tip for ARiSE researchers:** lightweight inference / surrogate workloads
> typically fit within *Trial use*. Pair Fugaku with the
> [AI for Science Supercomputer](https://github.com/RIKEN-RCCS/Rikyu) when GPU
> acceleration or the latest DL frameworks are required.

---

## Documentation

### Official Documentation

- [User guides (R-CCS)](https://www.r-ccs.riken.jp/en/fugaku/user-manuals/)

### HPCI Docs

- [Supercomputer Fugaku](https://www.hpci-office.jp/en/using_hpci/hardware_software_resource/2026/r-ccs_riken_2026-2)

### Community / GitHub Docs

- [Fugaku documentation repo](https://github.com/RIKEN-RCCS/fugaku-doc/tree/main/docs)

---

## System Access

### Interactive / Web

- [onDemand](https://github.com/RIKEN-RCCS/ondemand_fugaku) and
  [onDemand demo](https://github.com/RIKEN-RCCS/ondemand_fugaku_demo)

### CLI

- SSH access (standard HPC workflow)

### Programmatic

- [REST API](https://github.com/RIKEN-RCCS/fugaku-api)

---

## Software Ecosystem

### Package Management

- [Spack](https://github.com/RIKEN-RCCS/spack) (when using sysroot'd LLVM
  please refer to [LLVM toolchain via Spack](https://github.com/RIKEN-RCCS/PrivLLVMSpack))

### Compilers

- [Fujitsu Compiler (FCC/FORTRAN/C++)](https://www.r-ccs.riken.jp/fugaku/docs/user-guide/prog-guide/pdf/en/programming_common_part_programming_guide.pdf)
- GNU toolchain (via OS and Spack)
- LLVM toolchain

### MPI / Parallel Runtime

- Fujitsu MPI (MPI-3 compliant)
- OpenMP support on A64FX

---

## Containerization

- [Singularity / Apptainer guide](https://github.com/RIKEN-RCCS/fugaku-singularity-guide)

---

## Libraries

### Core HPC / Vendor Libraries

- **Fujitsu Software Technical Computing Suite (TCSDS)**
  - **BLAS / LAPACK / ScaLAPACK**
  - **FFTW** (Fujitsu-optimized)
  - **SSL2 math libraries** (A64FX optimized)
- **Fujitsu MPI** (MPI-3 compliant)
- [**MPICH-Tofu**](https://github.com/yutaka-ishikawa/mpich-tofu) (alternative MPI implementation)

  More details: [Fugaku Software Documentation](https://www.hpci-office.jp/en/using_hpci/hardware_software_resource/2026/r-ccs_riken_2026-2)

### Data / I/O Libraries

- **HDF5** → [Fugaku HDF5 Documentation](https://www.hpci-office.jp/en/for_users/appli_software)
- **NetCDF** → [Fugaku NetCDF Documentation](https://www.hpci-office.jp/en/for_users/appli_software)
- **ADIOS2** → [Fugaku ADIOS2 Documentation](https://www.hpci-office.jp/en/for_users/appli_software)
- **h5py** → [Fugaku h5py Documentation](https://www.hpci-office.jp/en/for_users/appli_software)

### Scientific Python Stack

- **Python · NumPy · SciPy · mpi4py · xarray · ASE** →
  [Fugaku Python Modules](https://www.hpci-office.jp/en/using_hpci/hardware_software_resource/2026/r-ccs_riken_2026-2)

Fugaku provides these libraries via **Spack** and pre-installed system environments.

---

## ★ AI / Machine Learning on Fugaku (Highlight)

> This section consolidates Fugaku's AI/ML software stack, including the
> **DL4Fugaku** project's A64FX-optimized backends and the latest evaluation
> activities. It is a primary reference for ARiSE / AI for Science researchers
> who plan to run inference, surrogate, or agentic workloads on Fugaku.

### Deep Learning Frameworks (HPCI-distributed builds)

- **PyTorch** (A64FX-optimized) → [PyTorch at Fugaku](https://www.hpci-office.jp/en/for_users/appli_software)
- **TensorFlow** (A64FX-optimized) → [TensorFlow at Fugaku](https://www.hpci-office.jp/en/for_users/appli_software)
- **Horovod** (distributed training) → [Horovod at Fugaku](https://www.hpci-office.jp/en/for_users/appli_software)

These builds incorporate the optimizations described below; users do not
typically need to compile their own framework.

### DL4Fugaku · oneDNN on A64FX

[DL4Fugaku](https://github.com/fujitsu/dnnl_aarch64) is the long-running effort
to deliver a production-quality deep-learning stack on A64FX. It centers on a
Fujitsu-maintained **oneDNN (Deep Neural Network Library)** port that targets
A64FX's SVE (Scalable Vector Extension) units, exploiting SIMD-width-512
operations and HBM2 bandwidth.

Key components:

- **oneDNN-A64FX** — A64FX-tuned primitives for convolution, GEMM, batched
  matmul, attention, and quantized inference; called by both PyTorch and
  TensorFlow framework backends.
- **PyTorch backend integration** — vectorized JIT kernels, GLOO/MPI for
  multi-node, mixed-precision (BF16 / FP16) where SVE permits.
- **TensorFlow backend integration** — XLA + oneDNN fused operators.
- **Best-practice tuning guides** — process / thread placement, NUMA pinning,
  memory-bandwidth-bound layer sizing, communication overlap.

Recommended starting points:

- DL4Fugaku project: <https://github.com/fujitsu/dnnl_aarch64>
- oneDNN upstream (Intel) with A64FX port: <https://github.com/oneapi-src/oneDNN>
- A64FX SVE tuning techniques: <https://github.com/RIKEN-RCCS/A64FX_Tuning_Techniques>

### Distributed Training & Inference

- **Horovod** for data-parallel training over **Tofu-D** interconnect.
- Process / thread layout recipes for A64FX (4 CMG × 12 cores) — see the
  [User Guides (R-CCS)](https://www.r-ccs.riken.jp/en/fugaku/user-manuals/)
  and the [A64FX tuning techniques](https://github.com/RIKEN-RCCS/A64FX_Tuning_Techniques).
- **Apptainer** containers for reproducible PyTorch / TensorFlow stacks
  (see [singularity guide](https://github.com/RIKEN-RCCS/fugaku-singularity-guide)).

### LLM Inference Evaluation on A64FX

- **ollama on A64FX (re-evaluation, ongoing).** Recent versions of
  [ollama](https://github.com/ollama/ollama) and the underlying
  [llama.cpp](https://github.com/ggerganov/llama.cpp) have substantially
  improved ARM64 / SVE support. We are re-evaluating modern small-to-mid
  scale LLMs (7B / 13B / 30B class, GGUF-quantized) on A64FX nodes.
  Progress, build recipes, and benchmark results will be published in the
  [F-DATA](https://github.com/RIKEN-RCCS/F-DATA) and
  [A64FX Tuning Techniques](https://github.com/RIKEN-RCCS/A64FX_Tuning_Techniques)
  repos and on this page.
- **vLLM / Triton Inference Server.** Currently targeted at GPU systems
  (see the [AI for Science Supercomputer](https://github.com/RIKEN-RCCS/Rikyu));
  Fugaku is positioned for CPU-side inference and surrogate workloads.

### AI for Science Use Cases

- Surrogate models (fast physics approximation)
- Physics-Informed Neural Networks (PINN)
- Hybrid HPC × AI workflows (simulation generates training data; AI accelerates
  inner loops)
- Distributed inference for agentic / scientific workflows

### Selected Papers / Resources

- Catalog of DL4Fugaku-related publications and benchmarks: see
  <https://github.com/fujitsu/dnnl_aarch64> and
  [R-CCS Fugaku results](https://www.r-ccs.riken.jp/en/fugaku/research/).
- A64FX architecture / performance papers (Fujitsu Technical Review):
  <https://www.fujitsu.com/global/about/resources/publications/technicalreview/>

> _Have a paper, recipe, or notebook to share? Please open a PR against this
> README — the AI/ML section is updated rolling._

---

## HPC Applications

### Molecular Dynamics

- **GROMACS** → [GROMACS at Fugaku](https://www.hpci-office.jp/en/for_users/appli_software/appli_gromacs)
- **LAMMPS** → [LAMMPS at Fugaku](https://www.hpci-office.jp/en/for_users/appli_software/appli_lammps)
- **NAMD** → [NAMD at Fugaku](https://www.hpci-office.jp/en/for_users/appli_software)
- **AMBER** → [AMBER at Fugaku](https://www.hpci-office.jp/en/for_users/appli_software)
- **GENESIS** (R-CCS) → [GENESIS at R-CCS](https://www.r-ccs.riken.jp/en/research/labs/cbrt/index.html)

### Quantum Chemistry / Electronic Structure

- **Quantum ESPRESSO** → [Quantum ESPRESSO on Fugaku](https://www.hpci-office.jp/en/for_users/appli_software/appli_qe/qe_r-ccs_riken-2)
- **ABINIT** → [ABINIT at Fugaku](https://www.hpci-office.jp/en/for_users/appli_software)
- **NWChem** → [NWChem at Fugaku](https://www.hpci-office.jp/en/for_users/appli_software)
- **NTChem** (R-CCS) → [NTChem at R-CCS](https://www.r-ccs.riken.jp/labs/lpnctrt/)
- **Gaussian** (commercial) → [Gaussian on Fugaku](https://www.hpci-office.jp/en/for_users/appli_software)
- **SMASH** → [SMASH at Fugaku](https://www.hpci-office.jp/en/for_users/appli_software/appli_smash)

### Materials Science / Condensed Matter

- **VASP** → [VASP at Fugaku](https://www.hpci-office.jp/en/for_users/appli_software)
- **Quantum ESPRESSO** → [Quantum ESPRESSO on Fugaku](https://www.hpci-office.jp/en/for_users/appli_software/appli_qe/qe_r-ccs_riken-2)
- **OpenMX** → [OpenMX at Fugaku](https://www.hpci-office.jp/en/for_users/appli_software/appli_openmx)
- **SALMON** → [SALMON at Fugaku](https://www.hpci-office.jp/en/for_users/appli_software/appli_salmon)
- **CP2K** → [CP2K at Fugaku](https://www.hpci-office.jp/en/for_users/appli_software)
- **Phonopy** → [Phonopy at Fugaku](https://www.hpci-office.jp/en/for_users/appli_software/appli_phonopy/)
- **ALAMODE** → [ALAMODE at Fugaku](https://www.hpci-office.jp/en/for_users/appli_software/appli_alamode)

### Computational Fluid Dynamics (CFD)

- **OpenFOAM** → [OpenFOAM at Fugaku](https://www.hpci-office.jp/en/for_users/appli_software/appli_openfoam)
- **FrontFlow/blue** (R-CCS) → [FrontFlow/blue at Fugaku](https://www.hpci-office.jp/en/for_users/appli_software/appli_frontflowblue)
- **ANSYS Fluent** (commercial) → [ANSYS Fluent at Fugaku](https://www.hpci-office.jp/en/for_users/appli_software)
- **Simcenter STAR-CCM+** → [Simcenter STAR-CCM+ at Fugaku](https://www.hpci-office.jp/en/for_users/appli_software)

### Weather / Climate

- **SCALE** (R-CCS) → [SCALE at R-CCS](https://scale.riken.jp/)
- **WRF** → [WRF at Fugaku](https://www.hpci-office.jp/en/for_users/appli_software)
- **NEMO** → [NEMO at Fugaku](https://www.hpci-office.jp/en/for_users/appli_software)

### Bioinformatics

- **BWA** → [BWA at Fugaku](https://www.hpci-office.jp/en/for_users/appli_software)
- **SAMtools** → [SAMtools at Fugaku](https://www.hpci-office.jp/en/for_users/appli_software)
- **BEDTools** → [BEDTools at Fugaku](https://www.hpci-office.jp/en/for_users/appli_software)
- **Picard** → [Picard at Fugaku](https://www.hpci-office.jp/en/for_users/appli_software)

Bioinformatics tools are available via **system modules** or **Spack**.

### Visualization / Analysis Applications

- **ParaView** → [ParaView at Fugaku](https://www.hpci-office.jp/en/for_users/appli_software)
- **VisIt** → [VisIt at Fugaku](https://www.hpci-office.jp/en/for_users/appli_software)
- **VMD** → [VMD at Fugaku](https://www.hpci-office.jp/en/for_users/appli_software)
- **PyMOL** → [PyMOL at Fugaku](https://www.hpci-office.jp/en/for_users/appli_software)

These are pre-installed on Fugaku as part of the **visualization suite**.

### Notes on Availability

- Fugaku provides:
  - Open-source software via **Spack** and pre-built environments
  - R-CCS-developed applications
  - Commercial ISV software (license required)

For a **full list of software** and availability, check the **HPCI Software Resource** page:

- [HPCI Software Resource](https://www.hpci-office.jp/en/using_hpci/hardware_software_resource/2026/r-ccs_riken_2026-2)

---

## Datasets

- [F-DATA](https://github.com/RIKEN-RCCS/F-DATA) — A Fugaku workload dataset
  for job-centric predictive modelling in HPC systems.
- Data repositories (R-CCS projects): <https://www.r-ccs.riken.jp/en/research/>

---

## Benchmarks

- HPL-AI / HPL-MxP: <https://github.com/RIKEN-RCCS/hpl-ai>
- Fugaku benchmark results: <https://www.r-ccs.riken.jp/en/fugaku/research/>
- TOP500 entry: <https://www.top500.org/system/179807/>
- DL4Fugaku & AI/ML benchmarks: see the
  [AI / Machine Learning on Fugaku](#-ai--machine-learning-on-fugaku-highlight)
  section.

---

## Hardware

### Compute

- A64FX tuning guides: <https://github.com/RIKEN-RCCS/A64FX_Tuning_Techniques>
- A64FX architecture (Fujitsu): <https://www.fujitsu.com/global/products/computing/servers/supercomputer/a64fx/>

### Network

- Tofu Interconnect D overview: <https://www.r-ccs.riken.jp/en/fugaku/about/>
- Technical paper (Fujitsu): <https://www.fujitsu.com/global/about/resources/publications/technicalreview/>

### Storage

- Fugaku S3-compatible service: <https://github.com/RIKEN-RCCS/fugaku-s3-service-guide>
- Parallel file system (Lustre-based, internal)

---

## Development & Optimization

- Performance tuning: <https://github.com/RIKEN-RCCS/A64FX_Tuning_Techniques>
- Profiling tools:
  - Fujitsu profiler
  - Arm MAP / Performance Reports

---

## Related Projects & Initiatives

- **AI for Science Supercomputer** (GPU companion system, ARiSE platform):
  <https://github.com/RIKEN-RCCS/Rikyu>
- **RiVault** (RIKEN AI inference gateway): <https://github.com/RIKEN-RCCS/RiVault>
- Fugaku co-design program: <https://www.r-ccs.riken.jp/en/fugaku/fs2020/>
- Post-Fugaku / next-gen HPC research: <https://www.r-ccs.riken.jp/en/>

---

## Citation / Acknowledgment

If you use Fugaku resources, please follow the
[HPCI acknowledgment guidelines](https://www.hpci-office.jp/en/for_users/hpci_info_manuals/acknowledgement).
