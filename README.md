<!-- Draft version by Peter HU -->

# CPU Scheduling Literature Review

(SCP, SMP, HMP) CPU Scheduling Model and Algorithm / Architectural design.

## [Background](./Goal/HMPSchedinbig.LITTLEContext.md)

## Pipeline for Literature Review

Paper Selection -- Taxonomy label -- Filter -- Annotate -- Summary

Ref: Systematic Literature Review (Webster&Watson, 2002)

- [File Name Taxonomy](./Goal/FileNameTaxonomy.md)

# Literature Review navigation by methods

- [CPU Power Model Focus](Algo-Basic/ModelFocus.md)

- [Category](Algo-Basic/Category.md)

## Efficient CPU resources operating Methods

## 1. Scheduler (OS)

* different Task Models for CPU tasks (individual, parallel or with dependencies)
* Scheduling algorithm (List, Federated algorithm, etc)
* Energy Effiency in HMP (with inter/intra-Migration)
* Consider for related factors (Temp, Resource Contentions, fairness, etc)

[Scheduler / Scheduling Algorithm  --- Details ---](Sched/Sched.md)

## 2. DVFS (cpufreq governor)

Resource Slowdown

- Energy-Delay tradeoff
  - quadratic relationship between voltage and dynamic power ↓
  - whereas a linear relationship between voltage and delay ↑.
- Problems
  - More leakage energy
  - Memory and other IO interfaces need to be active

*Single Core from 1995 (SCP)*

    Math Model and Algorithm Design, with some extensiable to HMP

- The energy minimization problem of scheduling n tasks with release times and deadlines on a single-core processor that can vary its speed dynamically where preemption is allowed.

[Single Core DVFS from 1995 --- Details ---](./DVFS/SCP-DVFS-from-1995.md)

*Multi-Core (MP)*

- proved the NP-hardness of the multi-core DVS problem when tasks could not migrate and gave several approximation algorithms for various special cases.

[Multi-core DVFS --- Details ---](./DVFS/MP-DVFS.md)

*Heterogeneous Multi-Core (HMP)*

**Category for HMP**

- from the program count perspective,
  - single program (programs per core <= 1)
  - multi-programs (programs per core > 1)
- from the application type perspective,
  - serial
  - parallel

Ref: Fairness-Aware Energy Efficient Scheduling on Heterogeneous Multi-Core Processors (2021).

## 3. Dynamic Resource Sleep (OS)

Resource Shutdown / Dynamic Power Management / Idle Management

- When a system is idle, it can be transitioned into a low-power sleep state.

  - Problems: switching between idle and active state exists cost.
- Dynamic Resource Sleep management: min-gap strategy.

[DRS  --- Details ---](./DRS/DRS.md)

More along this line can be found in the *Surveys ( 2010, 2011, S. Albers )*


## 4. The System-Wide Energy-Saving Model

Model with Algorithm design

- [Thermal Model and DVFS Algorithm --- Details ---](./DVFS/DVFS-Thermal-Models.md)

- [Memory Model and DVFS Algorithm  --- Details ---](./DVFS/DVFS-Memory-Models.md)

- [HMP Models (TODO) --- Details ---](./DVFS/HMP-DVFS-ToDo.md)

## Appendix A: HMP-Product-related improvements on EAS

[HMP-EAS-Improvements (First-Draft)  --- Details ---](./DVFS/HMP-EAS-Improvements.md)

## Appendix B: Tools for Power Monitoring and/or Power Controlling

See Vendors Folder

CPU

- RAPL-Running Average Power Limit (Intel)
  - DVFS mechanism and clock throttling
  - control and monitor power domains including PP0—CPU cores, DRAM—memory, and PKG—representing the whole CPU socket [see 2022](./Vendors/Intel-RAPL-2022-Krzywaniak.pdf) to dynamically adjust frequency scaling [see Powercap](./Vendors/Intel-RAPL-powercap.pdf)
- APM-Application Performance Monitoring (AMD)
- EnergyScale (IBM)

GPU

- NVML-NVIDIA Management Library / nvidia-smi8

## Appendix C: Survey

Review-Energy-Efficient-Algorithms-2010    S. Albers, Energy-efficient algorithms, Commun. ACM 53 (5) (2010) 86–96.

 [Survey-DVFS-2011](./Survey/Survey-Algorithms-for-DynamicSpeedScaling-2011.pdf)   S. Albers, Algorithms for dynamic speed scaling, in: Proceedings of International Symposium on Theoretical Aspects of Computer Science (STACS), 2011,  pp. 1–11.

[Survey-EAS-for-HPCS-2023](./Survey/Survey-EAS-for-HPCS-2023.pdf)  Energy-Aware Scheduling for High-Performance Computing Systems: A Survey (2023)

Survey-2014-ORNL-Energy-Embedded

### Feature Article on Utilization

  2019-Energy-Aware_Core_Switching_for_Mobile_Devices_with_a_Heterogeneous_Multicore_Processor

- Frequency vs Utilization (conflicting>)
- Need to be careful when there are no jobs, could be a lower untilization than expected.
