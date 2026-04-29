# Fugaku

This landing page provides an overview of the Supercomputer Fugaku operated by
[RIKEN R-CCS](https://www.r-ccs.riken.jp/en/). It aggregates publicly available
resources, software, and documentation. More detailed materials are available
to approved users through official access programs.

> **What's new (2026-04):** AI/ML workflows on A64FX are under continuous
> update. See **[AI / Machine Learning on Fugaku](#-ai--machine-learning-on-fugaku-highlight)**
> below for links to the official Fugaku AI framework guides and current
> status notes.

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
- [Fugaku AI framework guide (JP)](https://riken-rccs.github.io/fugaku-doc/docs/user-guide/sys-use/fugakuaiguide/build/ja/index.html)

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

- **HDF5**
- **NetCDF**
- **ADIOS2**
- **h5py**

Reference (official software lists):

- [HPCI Pre-installed application software](https://www.hpci-office.jp/en/for_users/appli_software)
- [Fugaku Spack guide (source)](https://github.com/riken-rccs/fugaku-doc/tree/main/docs/user-guide/sys-use/fugakuspackguide)

### Scientific Python Stack

- **Python · NumPy · SciPy · mpi4py · xarray · ASE**

Reference:

- [HPCI Hardware/Software resource (Fugaku)](https://www.hpci-office.jp/en/using_hpci/hardware_software_resource/2026/r-ccs_riken_2026-2)
- [Fugaku Spack guide (source)](https://github.com/riken-rccs/fugaku-doc/tree/main/docs/user-guide/sys-use/fugakuspackguide)

Fugaku provides these libraries via **Spack** and pre-installed system environments.

---

## ★ AI / Machine Learning on Fugaku (Highlight)

> This section consolidates Fugaku's AI/ML software stack, including the
> public A64FX optimization references and current evaluation notes. It is a
> primary reference for ARiSE / AI for Science researchers who plan to run
> inference, surrogate, or agentic workloads on Fugaku.

### Deep Learning Frameworks (HPCI-distributed builds)

- **PyTorch** (A64FX-related guide) → [PyTorch on the Fugaku (JP)](https://riken-rccs.github.io/fugaku-doc/docs/user-guide/sys-use/fugakuaiguide/build/ja/pytorch.html)
- **TensorFlow** (A64FX-related guide) → [TensorFlow on the Fugaku (JP)](https://riken-rccs.github.io/fugaku-doc/docs/user-guide/sys-use/fugakuaiguide/build/ja/tensorflow.html)
- **Horovod** (distributed training) → [Fugaku AI framework guide (JP)](https://riken-rccs.github.io/fugaku-doc/docs/user-guide/sys-use/fugakuaiguide/build/ja/index.html)

These builds incorporate the optimizations described below; users do not
typically need to compile their own framework.

### oneDNN / A64FX optimization references

Publicly available references for oneDNN and A64FX optimizations include the
following repositories and guides:

Key components:

- **fujitsu/dnnl_aarch64** — AArch64/SVE向け deep-learning kernel 実装。
- **fujitsu/pytorch** — Fugaku向けPyTorch関連情報。
- **fujitsu/tensorflow** — Fugaku向けTensorFlow関連情報。
- **RIKEN-RCCS/A64FX_Tuning_Techniques** — A64FX最適化の実践情報。

Recommended starting points:

- fujitsu/dnnl_aarch64: <https://github.com/fujitsu/dnnl_aarch64>
- fujitsu/pytorch: <https://github.com/fujitsu/pytorch>
- fujitsu/tensorflow: <https://github.com/fujitsu/tensorflow>
- oneDNN upstream: <https://github.com/oneapi-src/oneDNN>
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
  improved ARM64 / SVE support. Evaluation on A64FX is ongoing.
  Public update channels are this repository and related official Fugaku
  documentation pages.
- **vLLM / Triton Inference Server.** Currently targeted at GPU systems
  (see the [AI for Science Supercomputer](https://github.com/RIKEN-RCCS/Rikyu));
  Fugaku is positioned for CPU-side inference and surrogate workloads.
- **dalotia** is a [data loader library](https://github.com/RIKEN-RCCS/dalotia/)
  for tensors to easily integrate inference pipelines into scientific apps

### AI for Science Use Cases

- Surrogate models (fast physics approximation)
- Physics-Informed Neural Networks (PINN)
- Hybrid HPC × AI workflows (simulation generates training data; AI accelerates
  inner loops)
- Distributed inference for agentic / scientific workflows

### Selected Papers / Resources

- AI framework references: see
  <https://riken-rccs.github.io/fugaku-doc/docs/user-guide/sys-use/fugakuaiguide/build/ja/index.html> and
  [R-CCS Fugaku research / achievements](https://www.r-ccs.riken.jp/en/fugaku/research/).
- A64FX architecture / performance papers (Fujitsu Technical Review):
  <https://www.fujitsu.com/global/about/resources/publications/technicalreview/>

> _Have a paper, recipe, or notebook to share? Please open a PR against this
> README — the AI/ML section is updated rolling._

---

## HPC Applications

### Molecular Dynamics

- **GROMACS**
- **LAMMPS**
- **NAMD**
- **AMBER**
- **GENESIS** (R-CCS)

### Quantum Chemistry / Electronic Structure

- **Quantum ESPRESSO**
- **ABINIT**
- **NWChem**
- **NTChem** (R-CCS)
- **Gaussian** (commercial)
- **SMASH**

### Materials Science / Condensed Matter

- **VASP**
- **Quantum ESPRESSO**
- **OpenMX**
- **SALMON**
- **CP2K**
- **Phonopy**
- **ALAMODE**

### Computational Fluid Dynamics (CFD)

- **OpenFOAM**
- **FrontFlow/blue** (R-CCS)
- **ANSYS Fluent** (commercial)
- **Simcenter STAR-CCM+**

### Weather / Climate

- **SCALE** (R-CCS)
- **WRF**
- **NEMO**

### Bioinformatics

- **BWA**
- **SAMtools**
- **BEDTools**
- **Picard**

Bioinformatics tools are available via **system modules** or **Spack**.

### Visualization / Analysis Applications

- **ParaView**
- **VisIt**
- **VMD**
- **PyMOL**

These are pre-installed on Fugaku as part of the **visualization suite**.

Application list references (official):

- [HPCI Pre-installed application software](https://www.hpci-office.jp/en/for_users/appli_software)
- [HPCI Hardware/Software resource (Fugaku)](https://www.hpci-office.jp/en/using_hpci/hardware_software_resource/2026/r-ccs_riken_2026-2)

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
- Additional public technical references: <https://www.r-ccs.riken.jp/en/fugaku/research/>

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
