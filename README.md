# Fugaku

This landing page provides an overview of the Supercomputer Fugaku operated by RIKEN R-CCS.
It aggregates publicly available resources, software, and documentation. More detailed
materials are available to approved users through official access programs.

- Official Fugaku portal:
  https://www.r-ccs.riken.jp/en/fugaku/
- RIKEN R-CCS homepage:
  https://www.r-ccs.riken.jp/en/

---

## Overview

Fugaku is a flagship exascale-class supercomputer developed by RIKEN R-CCS in collaboration
with Fujitsu. It is powered by the A64FX ARM-based processor and is designed for high-performance
computing (HPC), AI workloads, and data-centric science.

- Architecture overview:
  https://www.r-ccs.riken.jp/en/fugaku/architecture/
- Performance and benchmarks:
  https://www.r-ccs.riken.jp/en/fugaku/results/

---

## Account / Time Application

Access to Fugaku is managed through HPCI:

- Fee-based Access  
  https://www.hpci-office.jp/en/using_hpci/proposal_submission_current/fugaku_fee_based

- Trial Access  
  https://www.hpci-office.jp/en/using_hpci/proposal_submission_current/fugaku_trial

- General HPCI portal  
  https://www.hpci-office.jp/

---

## Documentation

### Official Documentation
- User guides (R-CCS):
  https://www.r-ccs.riken.jp/en/fugaku/docs/
- FAQ:
  https://www.r-ccs.riken.jp/en/fugaku/faq/

### Community / GitHub Docs
- Fugaku documentation repo:
  https://github.com/RIKEN-RCCS/fugaku-doc/tree/main/docs

---

## System Access

### Interactive / Web
- onDemand:
  https://github.com/RIKEN-RCCS/ondemand_fugaku
- onDemand demo:
  https://github.com/RIKEN-RCCS/ondemand_fugaku_demo

### CLI
- SSH access (standard HPC workflow)

### Programmatic
- REST API:
  https://github.com/RIKEN-RCCS/fugaku-api

---

## Software Ecosystem

### Package Management
- Spack (Fugaku fork):
  https://github.com/RIKEN-RCCS/spack
- LLVM toolchain via Spack:
  https://github.com/RIKEN-RCCS/PrivLLVMSpack

### Compilers
- Fujitsu Compiler (FCC/FORTRAN/C++)
  https://www.fujitsu.com/global/products/computing/servers/supercomputer/development/
- GNU toolchain (via Spack)

### MPI / Parallel Runtime
- Fujitsu MPI (MPI-3 compliant)
- OpenMP support on A64FX

---

## Containerization

- Singularity / Apptainer guide:
  https://github.com/RIKEN-RCCS/fugaku-singularity-guide

---

## Libraries

### Core HPC / Vendor Libraries
- **Fujitsu Software Technical Computing Suite (TCSDS)**
  - **BLAS / LAPACK / ScaLAPACK**
  - **FFTW** (Fujitsu-optimized)  
  - **SSL2 math libraries** (A64FX optimized)
- **Fujitsu MPI** (MPI-3 compliant)
- **MPICH-Tofu** (alternative MPI implementation)  
  More details: [Fugaku Software Documentation](https://www.hpci-office.jp/en/using_hpci/hardware_software_resource/2026/r-ccs_riken_2026-2)

---

### Data / I/O Libraries
- **HDF5** → [Fugaku HDF5 Documentation](https://www.hpci-office.jp/en/for_users/appli_software/appli_hdf5)
- **NetCDF** → [Fugaku NetCDF Documentation](https://www.hpci-office.jp/en/for_users/appli_software/appli_netcdf)
- **ADIOS2** → [Fugaku ADIOS2 Documentation](https://www.hpci-office.jp/en/for_users/appli_software/appli_adios2)
- **h5py** → [Fugaku h5py Documentation](https://www.hpci-office.jp/en/for_users/appli_software/appli_h5py)

---

### Scientific Python Stack
- **Python** → [Fugaku Python Modules](https://www.hpci-office.jp/en/using_hpci/hardware_software_resource/2026/r-ccs_riken_2026-2)
- **NumPy** → [Fugaku Python Modules](https://www.hpci-office.jp/en/using_hpci/hardware_software_resource/2026/r-ccs_riken_2026-2)
- **SciPy** → [Fugaku Python Modules](https://www.hpci-office.jp/en/using_hpci/hardware_software_resource/2026/r-ccs_riken_2026-2)
- **mpi4py** → [Fugaku Python Modules](https://www.hpci-office.jp/en/using_hpci/hardware_software_resource/2026/r-ccs_riken_2026-2)
- **xarray** → [Fugaku Python Modules](https://www.hpci-office.jp/en/using_hpci/hardware_software_resource/2026/r-ccs_riken_2026-2)
- **ASE** → [Fugaku Python Modules](https://www.hpci-office.jp/en/using_hpci/hardware_software_resource/2026/r-ccs_riken_2026-2)

Fugaku provides these libraries via **Spack** and pre-installed system environments.

---

## HPC Applications

### Molecular Dynamics
- **GROMACS** → [GROMACS at Fugaku](https://www.hpci-office.jp/en/for_users/appli_software/appli_gromacs)
- **LAMMPS** → [LAMMPS at Fugaku](https://www.hpci-office.jp/en/for_users/appli_software/appli_lammps)
- **NAMD** → [NAMD at Fugaku](https://www.hpci-office.jp/en/for_users/appli_software/appli_namd)
- **AMBER** → [AMBER at Fugaku](https://www.hpci-office.jp/en/for_users/appli_software/appli_amber)
- **GENESIS** (R-CCS) → [GENESIS at R-CCS](https://www.r-ccs.riken.jp/labs/cbrt/)

---

### Quantum Chemistry / Electronic Structure
- **Quantum ESPRESSO** → [Quantum ESPRESSO on Fugaku](https://www.hpci-office.jp/en/for_users/appli_software/appli_qe/qe_r-ccs_riken-2)
- **ABINIT** → [ABINIT at Fugaku](https://www.hpci-office.jp/en/for_users/appli_software/appli_abinit)
- **NWChem** → [NWChem at Fugaku](https://www.hpci-office.jp/en/for_users/appli_software/appli_nwchem)
- **NTChem** (R-CCS) → [NTChem at R-CCS](https://www.r-ccs.riken.jp/labs/lpnctrt/)
- **Gaussian** (commercial) → [Gaussian on Fugaku](https://www.hpci-office.jp/en/for_users/appli_software/appli_gaussian)
- **SMASH** → [SMASH at Fugaku](https://www.hpci-office.jp/en/for_users/appli_software/appli_smash)

---

### Materials Science / Condensed Matter
- **VASP** → [VASP at Fugaku](https://www.hpci-office.jp/en/for_users/appli_software/appli_vasp)
- **Quantum ESPRESSO** → [Quantum ESPRESSO on Fugaku](https://www.hpci-office.jp/en/for_users/appli_software/appli_qe/qe_r-ccs_riken-2)
- **OpenMX** → [OpenMX at Fugaku](https://www.hpci-office.jp/en/for_users/appli_software/appli_openmx)
- **SALMON** → [SALMON at Fugaku](https://www.hpci-office.jp/en/for_users/appli_software/appli_salmon)
- **CP2K** → [CP2K at Fugaku](https://www.hpci-office.jp/en/for_users/appli_software/appli_cp2k)
- **Phonopy** → [Phonopy at Fugaku](https://www.hpci-office.jp/en/for_users/appli_software/appli_phonopy/)
- **ALAMODE** → [ALAMODE at Fugaku](https://www.hpci-office.jp/en/for_users/appli_software/appli_alamode)

---

### Computational Fluid Dynamics (CFD)
- **OpenFOAM** → [OpenFOAM at Fugaku](https://www.hpci-office.jp/en/for_users/appli_software/appli_openfoam)
- **FrontFlow/blue** (R-CCS CFD code) → [FrontFlow/blue at R-CCS](https://www.ciss.iis.u-tokyo.ac.jp/rss21/en/applications/)
- **ANSYS Fluent** (commercial) → [ANSYS Fluent at Fugaku](https://www.hpci-office.jp/en/for_users/appli_software/appli_ansys_fluent)
- **Simcenter STAR-CCM+** → [Simcenter STAR-CCM+ at Fugaku](https://www.hpci-office.jp/en/for_users/appli_software/appli_simcenter_starccm)

---

### Weather / Climate
- **SCALE** (R-CCS) → [SCALE at R-CCS](https://scale.riken.jp/)
- **WRF** → [WRF at Fugaku](https://www.hpci-office.jp/en/for_users/appli_software/appli_wrf)
- **NEMO** → [NEMO at Fugaku](https://www.hpci-office.jp/en/for_users/appli_software/appli_nemo)

---

### AI / Machine Learning
- **PyTorch** → [PyTorch at Fugaku](https://www.hpci-office.jp/en/for_users/appli_software/appli_pytorch)
- **TensorFlow** → [TensorFlow at Fugaku](https://www.hpci-office.jp/en/for_users/appli_software/appli_tensorflow)
- **Horovod** → [Horovod at Fugaku](https://www.hpci-office.jp/en/for_users/appli_software/appli_horovod)

Fugaku explicitly supports distributed ML workloads via **Horovod** and other distributed frameworks.

---

### Bioinformatics
- **BWA** → [BWA at Fugaku](https://www.hpci-office.jp/en/for_users/appli_software/appli_bwa)
- **SAMtools** → [SAMtools at Fugaku](https://www.hpci-office.jp/en/for_users/appli_software/appli_samtools)
- **BEDTools** → [BEDTools at Fugaku](https://www.hpci-office.jp/en/for_users/appli_software/appli_bedtools)
- **Picard** → [Picard at Fugaku](https://www.hpci-office.jp/en/for_users/appli_software/appli_picard)

Fugaku supports bioinformatics tools via **system modules** or **Spack** deployments.

---

### Visualization / Analysis Applications
- **ParaView** → [ParaView at Fugaku](https://www.hpci-office.jp/en/for_users/appli_software/appli_paraview)
- **VisIt** → [VisIt at Fugaku](https://www.hpci-office.jp/en/for_users/appli_software/appli_visit)
- **VMD** → [VMD at Fugaku](https://www.hpci-office.jp/en/for_users/appli_software/appli_vmd)
- **PyMOL** → [PyMOL at Fugaku](https://www.hpci-office.jp/en/for_users/appli_software/appli_pymol)

These are pre-installed on Fugaku as part of the **visualization suite**.

---

## Notes on Availability

- Fugaku provides:
  - Open-source software via **Spack** and pre-built environments
  - R-CCS-developed applications
  - Commercial ISV software (license required)

For a **full list of software** and availability, check the **HPCI Software Resource** page:
- [HPCI Software Resource](https://www.hpci-office.jp/en/using_hpci/hardware_software_resource/2026/r-ccs_riken_2026-2)

---

## Datasets

- F-DATA:
  https://github.com/RIKEN-RCCS/F-DATA  
  A Fugaku workload dataset for job-centric predictive modelling in HPC systems.

- Data repositories (R-CCS projects):
  https://www.r-ccs.riken.jp/en/research/

---

## Benchmarks

- HPL-AI / HPL-MxP:
  https://github.com/RIKEN-RCCS/hpl-ai

- Fugaku benchmark results:
  https://www.r-ccs.riken.jp/en/fugaku/results/

- TOP500 entry:
  https://www.top500.org/system/179807/

---

## Hardware

### Compute

- A64FX tuning guides:
  https://github.com/RIKEN-RCCS/A64FX_Tuning_Techniques

- A64FX architecture (Fujitsu):
  https://www.fujitsu.com/global/products/computing/servers/supercomputer/a64fx/

### Network

- Tofu Interconnect D overview:
  https://www.r-ccs.riken.jp/en/fugaku/architecture/

- Technical paper (Fujitsu):
  https://www.fujitsu.com/global/about/resources/publications/technicalreview/

### Storage

- Fugaku S3-compatible service:
  https://github.com/RIKEN-RCCS/fugaku-s3-service-guide

- Parallel file system (Lustre-based, internal)

---

## Development & Optimization

- Performance tuning:
  https://github.com/RIKEN-RCCS/A64FX_Tuning_Techniques

- Profiling tools:
  - Fujitsu profiler
  - Arm MAP / Performance Reports

---

## Related Projects & Initiatives

- Fugaku co-design program:
  https://www.r-ccs.riken.jp/en/fugaku/co-design/

- Post-Fugaku / next-gen HPC research:
  https://www.r-ccs.riken.jp/en/

---

## Citation / Acknowledgment

If you use Fugaku resources, please follow R-CCS acknowledgment guidelines:
https://www.r-ccs.riken.jp/en/fugaku/acknowledgement/
