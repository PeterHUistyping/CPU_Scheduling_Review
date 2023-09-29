# Heterogeneous Multi-Processing (HMP) scheduling algorithm in big.LITTLE Context
https://en.wikipedia.org/wiki/ARM_big.LITTLE

Background : CFS doesn't work well on heterogeneous processor architecture which uses two types of cores.
## Goal and Tool
Goal: Finding an algorithm better than what has been implemented so far.
The objective is twofold, namely to maximize the cumulative weight of tasks that can be completed before their deadlines and to minimize the total energy consumption

## What has been implemented.
1. CFS Completely Fair Scheduling:  
        RB Tree indexed by vruntime. -> Guarantees O(log(N))
2. EAS Energy Awareness Scheduling
        Considers energy implications

OS (Operating System) Scheduler, CPU DVFS (Dynamic Voltage and Frequency Scaling), and CPU Idle are commonly used to operate CPU resources efficiently. The underlying theory of these three solutions is to assign a given job to the appropriate HW resource, or to provide the appropriate HW resource for that job.   
State-of-the-art scheduling and CPU DVFS technology for mobile devices that best meets the needs of the times is EAS (Energy Aware Scheduling). Its main algorithm is to choose the best core or frequency that uses the least amount of energy to process the amount of job given. CPU Idle also has a same purpose in terms of choosing the idle states with minimum energy for a given idle time calculated by the scheduler.    
Although all of the above methods are expected to reduce the power consumption without performance degradation, in the real world, this method behaves differently than expected due to the characteristics of silicon, cache utilization, discrete range of frequency, and intentional frequency boosting.

## Proposal
1. Energy-Aware Scheduling for High-Performance Computing Systems: A Survey (2023)
A general idea of the roadmap
2. Performance Improvement of Linux CPU Scheduler Using Policy Gradient Reinforcement Learning for Android Smartphones (2020)
In LG G8 ThinQ, Learning EAS improved power consumption by 2.3% - 5.7%, hackbench results for process scheduling performance by 2.8% - 25.5%, applications entry time by 4.4% - 6.1%, and applications entry time under high CPU workload by 9.6% - 12.5%, respectively compared with EAS.
3. Load-aware Scheduling for Heterogeneous Multi-core Systems (2016)
With performance bench- marks, we showed that MCLAS does not fall behind CFS and a vanilla BFS that both do not support heterogeneous multi-core scheduling. Therefore, the presented scheduling approach is well suited for real-world challenges.
4. Idea from *distributed system* (2022)
Energy-aware online task dispatching and scheduling for edge systems with energy harvesting

 
## Past and Present
1. Brain Fuck Scheduler (BFS) : 
https://dl.acm.org/doi/pdf/10.1145/2851613.2851738
Unlike the CFS scheduler, BFS is O(n) scheduler which uses doubly linked list which is treated like a queue. 
So selection of the new process at time of context switch can go O(n) in the worst case 
and insertion of the process is O(1) as the queue is used. 
1. Per-Entity Load Tracking
A process can contribute to load even if it is not actually running at the moment; a process waiting for its turn in the CPU is an example. "Load" is also meant to be an instantaneous quantity — how much is a process loading the system right now? — as opposed to a cumulative property like CPU usage. A long-running process that consumed vast amounts of processor time last week may have very modest needs at the moment; such a process is contributing very little to load now, despite its rather more demanding behavior in the past.
1. Window Assisted Load Tracking  (Load is accounted using a geometric series)
As an alternative or additional load tracking scheme in lieu of or along with PELT (Load is accounted with a policy that observes past N windows), one that in our estimation better tracks task demand and CPU utilization especially for use cases on mobile devices.
## Reference 
1. EAS – Energy Aware Scheduler An unbiased look, Konsulko Group
2. Others have already been attached.