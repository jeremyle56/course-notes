# Virtual Memory II

## TLB Recap

TLB may or may not be under the operating system's control

- Hardware-loaded TLB - on a miss, hardware performs a page table lookup and reloads the TLB; e.g. Pentium
- Software-loaded TLB - on a miss, hardware generates a TLB miss exception, and exception handler reloads the TLB; e.g. MIPS

Even if the TLB is filled by software, it is still a hardware-based translator.

## Amdahl's Law

**Amdahl's law** states that overall performance improvement is limited by the fraction of time an enhancement can be used. So we should aim to make common cases fast.

![amdahl's law](15-12_amdahls-law.png)

## **MIPS R3000 TLB Handling omitted**
