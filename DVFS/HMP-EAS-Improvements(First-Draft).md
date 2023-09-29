<!-- Draft version by Peter HU -->

## Appendix: Product-related improvements on EAS 

### Multimedia

[Enhancing Energy Efficiency of Multimedia Applications in Heterogeneous Mobile Multi-Core Processors (2017)](../HMP/Initial-Draft-Productwise/Enhancing_Energy_Efficiency_of_Multimedia_Applications_in_Heterogeneous_Mobile_Multi-Core_Processors.pdf)

Ref:  Enhancing Energy Efficiency of Multimedia Applications in Heterogeneous Mobile Multi-Core Processors (2017),  IEEE & Samsung Electronics

- saves system-wide (not just CPU) energy consumption by 8.9 percent
- Allocates multimedia applications to the small cores and non-multimedia applications to the big cores.

### WAEAS

- improves 5-8% when the workload was high

[WAEAS_An_optimization_scheme_of_EAS_scheduler_for_wearable_applications](../HMP/Initial-Draft-Productwise/WAEAS_An_optimization_scheme_of_EAS_scheduler_for_wearable_applications.pdf)

Ref: An Optimization Scheme of EAS Scheduler for Wearable Applications  (2021), TSINGHUA SCIENCE AND TECHNOLOGY

1. BES-WALT Basic exponential smoothing-based WALT algorithm,
2. Energy-aware CPU selection algorithm,

- Adjusts Sched Tune
- Latency-Sensitive Task: decrease searching speed to get minimum performance capacity and the lowest idle state
- Non-Latency-Sensitive Task: not choose a lower utilization, but “task packing strategy”  ( on the little cores )

2. Batch processing strategy,

- Adjusts select idle sibling()
- Record and centralize on fewer cores

2. Cluster-based load balancing (overutilized)

- Reduces the meaningless task migration by local load balancing
- ( when having many aperiodic high-load applications )

### Reinforcement Learning

[Performance_Improvement_of_Linux_CPU_Scheduler_Using_Policy_Gradient_Reinforcement_Learning_for_Android_Smartphones.pdf](../HMP/Initial-Draft-Productwise/ML/Performance_Improvement_of_Linux_CPU_Scheduler_Using_Policy_Gradient_Reinforcement_Learning_for_Android_Smartphones.pdf)

Learning EAS, LG  Electronics

Ref: Performance Improvement of Linux CPU Scheduler Using Policy Gradient Reinforcement Learning for Android Smartphones (2020)

- improves power consumption by 2.8% - 7.8%
- Adjusts the TARGET_LOAD used to set the CPU frequency and the sched migration cost used as the task migration criteria
- Using Policy reinforcement learning dealing with workload or the ratio of sleep and running states changes.

KylinTune for Browser Engine

[KylinTune_DQN-based_Energy-efficient_Model_for_Browser_in_Mobile_Devices.pdf)](../HMP/Initial-Draft-Productwise/ML/KylinTune_DQN-based_Energy-efficient_Model_for_Browser_in_Mobile_Devices.pdf)

Ref: DQN-based Energy-efficient Model for Browser in Mobile Devices

- EAS and Q-table / Deep-Q Network (DQN) for setting schedtune.boost in Browser Engine
