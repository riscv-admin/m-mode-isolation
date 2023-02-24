# M-mode Isolation TG Charter

The M-mode Isolation Task Group is exploring the development of a Privileged ISA extension to support isolation within a hart between multiple workloads written to run in M-mode. Isolation includes memory and M-mode resources such as CSRs and the PMP. Potential use cases, requirements, and assumptions will be collected and analyzed. Any proposed extension shall scale across all RISC-V cores from low-end microcontrollers (RVM profile) to high-end applications processors (RVA profile). Extending isolation to the SoC is outside of the scope of this TG however the extension proposed by this TG shall be consistent with a RISC-V SoC domain isolation solution.

There are multiple scenarios that provide the impetus for M-mode isolation:

1. Multiple low-level machine-dependent M-mode software workloads are needed to run on the same hart. The workloads need isolation from each other for security and/or reliability reasons. For example, multiple entities in a supply-chain such as SoC vendor and OEM can develop workloads that need isolation. In another example, multiple groups within the same company can each develop workloads that need isolation.
2. The APP TEE TG specification shows the security monitor and firmware both running in M-mode. The firmware can be quite complex (e.g., networking stack) so running it in M-mode significantly increases the TCB’s attack surface. Isolating the security monitor from the firmware removes the firmware from the TCB.

The M-mode Isolation TG is developing a Privileged ISA extension to support isolation (memory and CSRs) between multiple workloads all written to run in M-mode. Potential use cases, requirements, and assumptions will be collected and analyzed. The extension will scale across all RISC-V cores from low-end microcontrollers (RVM profile) to high-end applications processors (RVA profile). The impetus for M-mode isolation stems from scenarios where multiple low-level machine-dependent M-mode software workloads run on the same processor. These multiple workloads require isolation from each other to meet security and/or reliability requirements. There can be multiple entities in a supply-chain such as SoC designer and OEM or even multiple groups within the same company developing M-mode workloads. In another scenario, there is the desire to reduce the attack surface of M-mode software by only running a subset of the software in M-mode. This implies the remainder of the M-mode software is ported to run in existing lower-privilege modes (called de-privileging). The software development effort to de-privilege existing M-mode software to improve security is a competitive disadvantage of RISC-V relative to other ISAs.

The M-mode Isolation TG will deliver a Priviledged ISA extension that provides M-mode Isolation for existing and new software.

The following items are presently not planned to be delivered as part of this work:

 1. Domain (AKA World) isolation within a Hart and within an SoC

To achieve its goals, the M-mode Isolation TG will interact with the following groups:

 1. Security HC
 2. Runtime Integrity SIG
 3. Trusted Compute SIG
 4. AP-TEE TG
 5. Privileged ISA Committee
