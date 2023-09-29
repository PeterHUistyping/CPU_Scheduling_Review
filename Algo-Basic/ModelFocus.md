## Power Model Focus

- Energy E
- $ P = P_{switching} + P_{static}$
- Dynamic Power $P_{switching} = \alpha f C_L V_{DD}^2$

  - Switching and Short-circuit power
  - $$
    E= P t =    \alpha f C_L V_{DD}^2 t =   \alpha C_L V_{DD}^2 \propto    \alpha C_L f^2
    $$

  As $V\propto f$ for the last step.
- Leakage power $P_{static} =  V_{DD} I_{Leakage} $ = $\beta$

  - Current that flows through the transistor when there is no activity.
  - Refresh power
  - Standby power
  - For instance, in DRAM (widely used as main memory), leakage power can be as much as 10 times of the dynamic read/write power on the memory chip using a process technology with the size smaller than 50nm (Wilton and Jouppi 1996)
- Load
- Performance: Deadline-aware, Fairness
- Shared Memory / Resource Contention

  - DRAM
  - Cache
- Complexity

  - O(1), O(n)
