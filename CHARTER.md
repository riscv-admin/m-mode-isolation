# M-mode Isolation TG Charter

The M-mode Isolation TG will develop one or more privileged ISA extensions to support isolation of M-mode software. The M-mode Isolation Task Group is exploring how to better support multiple M-mode workloads that require isolation from each other. For some use cases isolation is required for security, supply-chain, and/or reliability reasons. Isolation includes memory and M-mode resources such as CSRs and the PMP. A typical security use case is to remove some M-mode software such as runtime firmware from the TCB (Trusted Computing Base) when a SM (Secure Monitor) is also present in M-mode. A typical supply-chain use case is to isolate SoC developer software from OEM software. A typical reliability use case is to isolate multiple M-mode workloads to limit the scope of software and/or transient hardware faults in a workload.

One solution to M-mode Isolation is to de-privilege M-mode software to a lower-privilege mode such as S-mode or U-mode. De-privileging can be burdensome for software developers. It can also create unacceptable performance overheads due to limitiations of available functionality in those modes vs. M-mode. Alternative solutions or improvements to the current solution (e.g., improvements in S-mode to reduce functionality differences between M-mode and S-mode) will be explored. Potential use cases, requirements, and assumptions will be collected and analyzed. The M-mode Isolation TG will develop a solution to these use cases and requirements in the form of one or more privileged ISA extensions. The solution shall scale from low-end microcontrollers (RVM profile) up to high-end applications processors (RVA profile). 

At this time, a separate proposal to provide domain/world isolation within a hart and extend it to the SoC is anticipated. The solution proposed by the M-mode Isolation TG will likely interoperate with any domain/world isolation proposal to solve some use cases. Additionally, the solution proposed by the M-mode Isolation TG shall be consistent with the overall RISC-V Security Model.

To achieve its goals, the M-mode Isolation TG will be under the Privileged ISA Committee and interact with the following groups:

 1. Security HC (dotted-line)
 2. Runtime Integrity SIG
 3. Trusted Computing SIG
 4. AP-TEE TG
 6. SoC Infrastructure Committee
 7. Potential TG for domain/world isolation
