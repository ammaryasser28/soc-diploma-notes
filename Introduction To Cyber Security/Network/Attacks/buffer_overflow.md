# Buffer Overflow

## Overview
A **Buffer Overflow** is a vulnerability that occurs when a program writes more data to a memory buffer than it was designed to hold.  
The extra data overflows into adjacent memory locations, potentially overwriting critical information such as return addresses and control data.

This vulnerability exists in many types of software, including operating systems and applications, and has been widely exploited in real-world attacks.

---

## What Is a Buffer?
A buffer is a **chunk of memory** used by a program to temporarily store data.

Examples include:
- Arrays
- Strings
- User input variables

Example in C:
```c
char buffer[10];
```
This buffer can store only 10 bytes.

## Root Cause of Buffer Overflow

A buffer overflow occurs when:

- Input data exceeds the allocated buffer size
- No proper bounds checking is performed
- Extra data overwrites adjacent memory areas, leading to undefined or exploitable behavior

---

## Why Buffer Overflows Are Common in C/C++

Buffer overflows frequently occur in **C and C++** because:

- These languages do not perform automatic bounds checking
- They allow direct memory manipulation
- They trust the programmer to stay within memory limits

### Example
```c
char buffer[10];
gets(buffer);  // Unsafe function
```
If the user inputs 50 bytes:
- The program will not stop the write
- Memory corruption will occur

---


<img width="1115" height="443" alt="Screenshot 2026-01-15 102203" src="https://github.com/user-attachments/assets/562fac0e-7b4b-41a1-ae97-dd6c8f446511" />


## Normal Program Execution (Safe Case)

### Memory Layout (Simplified)
A | B | C | Q | Return Address | D


- **A, B, C, D**: Program instructions  
- **Q**: Buffer handling user input  
- **Return Address**: Location where execution continues after function completion  

### Normal Flow
1. Instructions at **A** and **B** execute normally
2. Instruction **C** calls a function that processes buffer **Q**
3. The function executes and reads user input safely
4. The function reaches the return instruction
5. Execution returns to instruction **D**
6. The program continues normally

---

## Buffer Overflow Exploitation (Attack Case)

In a vulnerable program:
- Buffer **Q** handles user input
- Input size is not validated

### Attack Flow
1. The attacker supplies input larger than buffer **Q**
2. Excess data overwrites adjacent memory
3. The **return address** is overwritten
4. The attacker injects malicious code (shellcode)
5. Execution flow is redirected to attacker-controlled code

---

## No-Operation (NOP) Sled

Attackers often use a **NOP sled**, which consists of repeated `NOP` instructions:

- `NOP` means “do nothing”
- Allows flexible landing space for execution
- The CPU slides through NOPs until the shellcode is reached

---

## Control Flow Hijacking

After overwriting the return address:
- The program executes a `RET` instruction
- Instead of returning to instruction **D**:
  - The CPU jumps to the malicious code
- The attacker’s payload executes

Attackers may later return execution back to **D** to avoid detection.

---

## Why Overwriting the Return Address Is Required

Processors do **not** execute code simply because it exists in memory.

- Code runs only when the **Instruction Pointer** (IP / EIP / RIP) points to it
- Injected shellcode remains inactive unless execution flow is redirected

Overwriting the return address forces the CPU to jump to attacker-controlled code.

---

## Impact

- Arbitrary code execution
- Privilege escalation
- System compromise
- Malware installation
- Bypassing security controls

Since the vulnerable program is legitimate, the operating system may treat malicious actions as normal behavior.

---

## Mitigation Techniques

- Bounds checking on all inputs
- Use safe functions (e.g., `fgets` instead of `gets`)
- Stack Canaries
- ASLR (Address Space Layout Randomization)
- DEP / NX Bit (Non-Executable Memory)
- Regular software updates and patching

---

## Summary

- Buffer overflow occurs due to improper memory bounds checking
- Common in low-level languages like C and C++
- Attackers overwrite return addresses to hijack execution flow
- Strong coding practices and modern protections mitigate the risk
