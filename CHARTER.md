# M-mode Isolation TG Charter

The M-mode Isolation Task Group is exploring the development of a Privileged ISA extension to support isolation between multiple workloads written to run in M-mode. Isolation includes memory and M-mode resources such as CSRs and the PMP. De-privileging an entire M-mode workload to S-mode results in an ecosystem burden to create and maintain M-mode and S-mode variants. Additionally, portions of the M-mode workload may depend on resources only available in M-mode.

Potential use cases, requirements, and assumptions will be collected and analyzed. Any proposed extension shall scale across all RISC-V cores from low-end microcontrollers (RVM profile) to high-end applications processors (RVA profile). Extending isolation to the SoC is outside of the scope of this TG however the extension proposed by this TG shall be consistent with a RISC-V SoC domain isolation solution and the overall RISC-V Security Model.

There are multiple scenarios that provide the impetus for M-mode isolation:

1. Multiple low-level machine-dependent M-mode software workloads are needed to run on the same hart. The workloads need isolation from each other for security and/or reliability reasons. For example, multiple entities in a supply-chain such as SoC vendor and OEM can develop workloads that need isolation. In another example, multiple groups within the same company can each develop workloads that need isolation.
2. Existing RISC-V firmware runs in M-mode and portions of it rely on resources only available in M-mode. Some of the security features being proposed for RISC-V add a SM (Security Monitor) also running in M-mode. Other ISAs have added a higher privilege level when adding security features that require a SM to provide isolation from the firmware. The firmware can be quite complex (e.g., networking stack) so running it in M-mode significantly increases the attack surface of the SM. The SM is the most trusted SW running on a hart so isolating it from the firmware removes the firmware from the TCB (Trusted Computing Base) and reduces the attack surface.

The M-mode Isolation TG will deliver a Priviledged ISA extension that provides M-mode Isolation for existing and new software.

The following items are presently not planned to be delivered as part of this work:

 1. Domain (AKA World) isolation within a Hart and within an SoC

To achieve its goals, the M-mode Isolation TG will interact with the following groups:

 1. Security HC
 2. Runtime Integrity SIG
 3. Trusted Compute SIG
 4. AP-TEE TG
 5. Privileged ISA Committee
