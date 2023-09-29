## Multi-Core Processor (MP) 

[SMP-AM-2012-Germany_Albers-DVFS](../SMP/SMP-AM-2012-Germany_Albers-DVFS.pdf)

Ref: S. Albers, F. Müller, S. Schmelzer, Speed scaling on parallel processors, Algorithmica 68 (2) (2014) 404–425.

- proved the NP-hardness of the multi-core DVS problem when tasks could not migrate and gave several approximation algorithms for various special cases.

### Model

Consider n jobs,

- Job i is specified by a release date $r(i),$ a deadline $d(i)$ .
- Job i can be feasibly scheduled in the time interval $[r(i),d(i))$.
- Processing volume $p(i)$, the amount of work that must be finished to complete the job.
- Have to be assigned to m parallel processors, each of which can independently operate at variable speed.
- Allow job preemption, disallow job migration.
- Power Consumption depends on processor's speed $s$

$$
P(s) = s^{p} , p \geq 2
$$

### Algorithm

First assign jobs to processors and then, on each processor, construct an optimal schedule for the job set assigned to it.

- Unit Size Jobs with Agreeable Deadlines

  - polynomial time algorithm : RR
  - jobs are first sorted according to their release dates and are then assigned to processors using Round Robin
- Unit Size Jobs with Arbitrary Release Dates and Deadlines (NP-hard)

  - Classified Round Robin

    - first divides the given jobs into classes such that each class job densities differ by a factor of at most 2
- Jobs with Arbitrary Processing volume Requirements $p(i)$

  - Earliest Deadline and List scheduling (Greedy)
  - Assign each job to the processor that currently has the smallest load.
- Online Algorithms

  - Apply a single processor online algorithm instead of constructing optimal schedules.

---- Appendix ----

See [Multi-core Processor (MP)](../MP/) Folder

- Linear Programming
- Max flow

[24] E. Angel, E. Bampis, F. Kacem, D. Letsios, Speed scaling on parallel processors with migration, J. Comb. Optim. 37 (4) (2019) 1266–1282.

[25] E. Bampis, A. Kononov, D. Letsios, G. Lucarelli, M. Sviridenko, Energy efficient scheduling and routing via randomized rounding, J. Sched. 21 (1) (2018) 35–51.

[26] S. Albers, A. Antoniadis, G. Greiner, On multi-processor speed scaling with migration, J. Comput. Syst. Sci. 81 (7) (2015) 1194–1209.

[27] V. Chau, X. Chen, K.C.K. Fong, M. Li, K. Wang, Flow shop for dual CPUs in dynamic voltage scaling, Theor. Comput. Sci. 819 (2020) 24–34.
