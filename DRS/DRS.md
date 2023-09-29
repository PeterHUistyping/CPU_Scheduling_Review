# Power-management Paradigm Choice

### 1. Race-to-halt

- It uses the **highest performance state** to complete the work, and immediately attempts to power down DVFS states
- rely on the assumption that tasks are compute bound (versus memory bound).

[17] M.A.AwanandS.M.Petters,“Enhancedrace-to-halt:Aleakage-aware energy management approach for dynamic priority systems,” in 23rd Euromicro Conference on Real-Time Systems, Jul. 2011, pp. 92–101.

### 2. Race-to-idle

- Modern processors can quickly power down regions of the CPU (power-gating)
- When a system is idle, it can be transitioned into a low-power sleep state by creating an idke period
- Problems: switching between idle and active state exists cost
- Goal: idle period is **long** enough (the energy savings in sleep state >  transition cost to the on state.)
- Tasks are memory-bound and need to be preemptive

[SMP-AM-2006-Taiwan-Chen-Leakage](../SMP/SMP-AM-2006-Taiwan-Chen-Leakage.pdf) Leakage-aware energy-efficient scheduling of real-time tasks in multiprocessor systems, J.-J. Chen, H.-R. Hsu, T.-W. Kuo, Proceedings of IEEE Real- Time and Embedded Technology and Applications Symposium (RTAS), 2006, pp. 408–417.

- When the overheads in turning on/off a processor are negligible
  - polynomial-time algorithm with a 1.283 approximation bound is proposed
- When the overheads are non-negligible
  - polynomial-time algorithms with a 2 approximation bound

*Dynamic Speed Scaling with Sleep state (DSS-S) ---  The first to combine DVFS + DRS*

[SCP-AM-2007-California_Irani-Sleep](../SCP/SCP-AM-2007-California_Irani-Sleep.pdf)

- Model : Processor state, Power P(0)
- Goal : **minize critical speed**
- an offline algorithm that is within a factor of 2 of the optimal algorithm.
- an online algorithm with a constant competitive ratio.

S. Irani, S. Shukla, R. Gupta, Algorithms for power savings, ACM Trans. Algorithms 3 (4) (2007).

#### Appendix1

[SCP-AM-2012-France-Bampis-Hibernate](../SCP/SCP-AM-2012-France-Bampis-Hibernate.pdf)

E. Bampis, C. Dürr, F. Kacem, I. Milis, Speed scaling with power down scheduling for agreeable deadlines, Sustain. Comput., Inform. Syst. 2 (4) (2012) 184–189.

[Race to idle: New algorithms for speed scaling with a sleep state](./Albers-2014-Race-to-Idle.pdf) S. Albers and A. Antoniadis, ACM Trans. Algorithms, vol. 10, no. 2, pp. 9:1–9:31, Feb. 2014.

[SCP-AM-2019-Germany_Antoniadis-sleep](../SCP/SCP-AM-2019-Germany_Antoniadis-Sleep.pdf)

A. Antoniadis, C. Huang, S. Ott, A fully polynomial-time approximation scheme for speed scaling with a sleep state, Algorithmica 81 (9) (2019) 3725–3745.

#### min-gap in execution for Gap Scheduling

- the device goes into a sleep state whenever it is idle
- Objective : **minimize the total number of transitions**
  - the time spent in the active state is fixed by the input jobs
  - stronger goal from the point of view of approximation algorithms

[SCP-2006-Unit_Tasks_Min_IdlePeriodsNum_Offline](../SCP/SCP-2006-Unit_Tasks_Min_IdlePeriodsNum_Offline.pdf) Scheduling unit tasks to minimize the number of idle periods: a polynomial time algorithm for offline dynamic power management,P. Baptiste, Proceedings of the 17th Annual ACM-SIAM (SODA), 2006, pp. 364–367.

- The optimal schedule bound, prove by contradiction
- Dynamic Programming

[SMP-2013-Minimize_Gaps](../SMP/SMP-2013-Minimize_Gaps.pdf)  Scheduling to minimize gaps and power consumption, E.D. Demaine, M. Ghodsi, M. Hajiaghayi, A.S. Sayedi-Roshkhar, M. Zadimoghaddam, J. Sched. 16 (2) (2013) 151–160.

- a special case of the multi-interval problem

#### Appendix2

[15] P. Baptiste, M. Chrobak, C. Dürr, Polynomial-time algorithms for minimum energy scheduling, ACM Trans. Algorithms 8 (3) (2012) 26:1–26:29.

[16] E. Angel, E. Bampis, V. Chau, Low complexity scheduling algorithms minimizing the energy for tasks with agreeable deadlines, Discrete Appl. Math. 175 (2014) 1–10.

### 3. ML-based adjustment between these two ideas

Advantage of *machine-learning*

- Converge to race-to-halt considering the workload/system combination, while still being able to adjust for more memory-bound or mixed workloads.

Two closest related areas of modern power management related to our work are QoSM middleware and machine learning-based power managers.

[HMP-SArch-2021-ETH_Giardino-Q-Learner_QoS_Manager](../HMP/HMP-SArch-2021-ETH_Giardino-Q-Learner_QoS_Manager.pdf)

2QoSM: A Q-Learner QoS Manager for Application-Guided Power-Aware Systems

- an abstraction of physical system performance (communication and path error), application state, and power consumption into a unitless state vector
- a C-based Q-learner-based Quality-of-Service Manager (2QoSM) that takes the state vector, and learns policies for system power management based upon tunable reward functions
- an evaluation of the 2QoSM on a MCSoC at the center of a power-constrained mobile robot showing significant improvement over both standard Linux power management and a state-of-the-art application-guided governor
- a demonstration of the utility of application, hardware, and policy agnostic middleware for embedded power management

#### Appendix3: ML method

    -----  Appendix : List of related literature ----

*Reinforcement Learning*[25] A. Das, M. J. Walker, A. Hansson, B. M. Al-Hashimi, and G. V. Merrett, “Hardware-software interaction for run-time power optimization: A case study of embedded linux on multicore smartphones,” in 2015 IEEE/ACM International Symposium on Low Power Electronics and Design (ISLPED). IEEE, Jul. 2015, pp. 165–170.

- optimal power state of a CPU

[26] J. F. Martinez and E. Ipek, “Dynamic multicore resource management: A machine learning approach,” IEEE Micro, vol. 29, no. 5, pp. 8–17, Sep. 2009.

- make low-level power management decisions including DRAM scheduling and multiresource allocation

[27] R. Ye and Q. Xu, “Learning-based power management for multicore pro- cessors via idle period manipulation,” IEEE Transactions on Computer- Aided Design of Integrated Circuits and Systems, vol. 33, no. 7, pp. 1043–1055, Jul. 2014.

- optimize idle periods to reduce power consumption in simulations of synthetic benchmarks, with goal to reduce transitions

[28] H. Shen, Y. Tan, J. Lu, Q. Wu, and Q. Qiu, “Achieving autonomous power management using reinforcement learning,” ACM Trans. Des. Autom. Electron. Syst., vol. 18, no. 2, pp. 24:1–24:32, Apr. 2013.

- pick DVFS states by constraining the performance and temperature while minimizing the total energy

[29] Y. Ge and Q. Qiu, “Dynamic thermal management for multimedia applications using machine learning,” in Proceedings of the 48th Design Automation Conference, ser. DAC ’11. New York, NY, USA: ACM, Jun. 2011, pp. 95–100.

- CPU metrics, user-constraints, and processor temperature for determining state and reward

[30] A. Das, B. M. Al-Hashimi, and G. V. Merrett, “Adaptive and hierarchical runtime manager for energy-aware thermal management of embedded systems,” ACM Trans. Embed. Comput. Syst., vol. 15, no. 2, pp. 24:1– 24:25, Jan. 2016.

- Q-Learner to allocate threads and set CPU frequency to obtain a given performance target [30]. Their work is focused on thermal limits and performance targets are time- based deadlines

[31] U. Gupta, S. K. Mandal, M. Mao, C. Chakrabarti, and U. Y. Ogras, “A deep q-learning approach for dynamic management of heterogeneous processors,” IEEE Computer Architecture Letters, vol. 18, no. 1, pp. 14–17, Jan. 2019.

- Deep Q-Learning (DQL) was used on a similar big.LITTLE single-board computer to obtain near- optimal performance per watt

  -----  Appendix : List of related literature ----
