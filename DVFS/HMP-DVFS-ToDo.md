## HMP Models (TO DO)

  [HMP-M-2013-Singapore_Pricopi-Model](../HMP/HMP-M-2013-Singapore_Pricopi-Model.pdf)

- power-performance model for commercial asymmetric multi-core.

  [HPM] [HMP-A-2013-USA_Pricopi-Hierarchical_power_management](../hmp/HMP-A-2013-USA_Pricopi-Hierarchical_power_management.pdf)
- *Control Theory, control-based framework*
- achieve the optimal performance-power trade-off
- with the aid of multiple PID controllers (one for each application and one for each cluster), considering the TDP (Thermal Design Power) budget.
- Cluster controller allocates the power budget to each cluster and the other controllers try to meet the TDP budget.
- However, for higher number of clusters, its performance degrades dramatically.

  [SmartBalance] [HMP-A-2015-USA_Sarma-SmartBalance_load_balancer_MPSoCs](../HMP/HMP-AM-2015-USA_Sarma-SmartBalance_load_balancer_MPSoCs.pdf)

  Ref:SmartBalance: A Sensing-Driven Linux **Load Balancer** for Energy Efficiency of Heterogeneous MPSoCs
- performs load balancing using a sense-predict-balance paradigm.
- closed loop
- introduce estimation and prediction models to calculate the performance and power impact of executing each thread on different heterogeneous cores without performing sampling at each core type.
- finer granularity: thread-level awareness



 
  [HFEE] [HMP-A-2021-Iran_Salami-FairEnergy-HFEE](../HMP/HMP-A-2021-Iran_Salami-FairEnergy-HFEE.pdf)
- · Fairness  · Energy efficiency

  Ref: Fairness-Aware Energy Efficient Scheduling on Heterogeneous Multi-Core Processors (2021).

  [CEEF] [HMP-A-2022-Iran_Salami-FairEnergyContention-CFEE](../HMP/HMP-A-2022-Iran_Salami-FairEnergyContention-CFEE.pdf)
- Consider · Shared resource contention · Energy efficiency · Fairness
- surpasses Linux and four other schedulers in terms of fairness (58%) and energy efficiency (37% on average)

  Ref: Online energy‐efficient fair scheduling for heterogeneous multi‐cores considering shared resource contention (2022)

  [HMP-A-2019-Hungary_Bringye-User-mode-CPUFreq-governor](../HMP/HMP-A-2019-Hungary_Bringye-User-mode-CPUFreq-governor.pdf)

  Power consumption aware big.LITTLE scheduler for Linux operating system

  [HMP-A-2020-Korea_Samsung_Park-Energy-Performance](../HMP/HMP-A-2020-Korea_Samsung_Park-Energy-Performance.pdf)

  Performance-efficient CPU resource management algorithm on Heterogeneous multi-processor
- PASE (Performance Aware Scheduling within a given Energy budget)
- Performance aware idle depth selection (PAI)
- a new idle state prediction method based on cache miss rate and relate frequency. That is, not only the energy consumed, but also the performance impact will be considered for selecting the idle state.

### ** DVFS **

The most common method of software-controlled DVFS (e.g. Linux on-demand governor) is to set a target system load, and adjust the P-States (discrete voltage/frequency pairs) to reach it.

  Linaro (Collaborative engineering organization consolidating and optimizing open source software and tools for ARM).

- EA-SU (Energy Aware SchedUtil)

  Power step-wise frequency scaling (PSF)

  [SMP-AM-2014-Intel_Rotem-EARtH](../SMP/SMP-AM-2014-Intel_Rotem-EARtH.pdf)

  Energy Aware Race to Halt: A Down to EARtH Approach for Platform Energy Management

  [HMP-AM-2016-Intel_Rotem-H-EARtH](../hmp/HMP-AM-2016-Intel_Rotem-H-EARtH.pdf)

  H-EARtH_Heterogeneous_Multicore_Platform_Energy_Management
- It offers a runtime scheduling and energy management algorithm for multicore heterogeneous CPUs to optimize the total platform E⋅D^α metric.

  [HMP-A-2020-Korea_Samsung_Park-Energy-Performance](../HMP/HMP-A-2020-Korea_Samsung_Park-Energy-Performance.pdf)

  Performance-efficient CPU resource management algorithm on Heterogeneous multi-processor
- Power step-wise frequency scaling (PSF)
- The goal of problem is to find the optimal path of series of OPP selection minimizing the energy consumption and latency to replace ‘x1.25’ is the previous DVFS with 25% margin

**More sophisticated strategies for controlling DVFS**

[12] S. Ahmed and B. H. Ferri, “Prediction-based asynchronous CPU-budget allocation for soft-real-time applications,” IEEE Transactions on Computers, vol. 63, no. 9, pp. 2343–2355, Sep. 2014.

- scheduling periodic workloads

[13] R. Ge, X. Feng, W. c. Feng, and K. W. Cameron, “CPU MISER: A performance-directed, run-time system for power-aware clusters,” in 2007 Int’l Conference on Parallel Processing (ICPP 2007), Sep. 2007.

- integrated runtime systems such as CPU MISER

[14] Q.Deng,D.Meisner,A.Bhattacharjee,T.F.Wenisch,andR.Bianchini, “CoScale: Coordinating CPU and memory system DVFS in server systems,” in 2012 45th Annual IEEE/ACM International Symposium on Microarchitecture, Dec. 2012, pp. 143–154.

- CoScale

[15] H.David,E.Gorbatov,U.R.Hanebutte,R.Khanna,andC.Le,“RAPL: Memory power estimation and capping,” in 2010 ACM/IEEE Interna- tional Symposium on Low-Power Electronics and Design (ISLPED), Aug. 2010, pp. 189–194.

- Intel’s RAPL system based upon energy quotas
