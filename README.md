# Assemblings

Welcome to Assemblings!
I need to learn ARM assembly, so I asked Claude.ai for a course outline.
I don't plan on following through up til the end but I just need it to get a good enough understanding to work with it.
Feel free to use this.

## Course Outline

**Phase 1: First Steps in ARMv7**
* **Exercise 1: Hello, Assembly!**
  * Write an empty program that exits with status code 0
  * **Concepts covered:** Program structure, `MOV` instruction, condition codes (AL), syscall using `SWI`
  * **Instructions:**
    1. Load syscall number for `exit` (1) into `r7`
    2. Load return code (0) into `r0`
    3. Make syscall with `SWI #0` or `SWI 0x900001`

* **Exercise 2: Register Basics**
  * Work with immediate values and registers
  * **Concepts covered:** Register naming (r0-r15), immediate values with `#`, limitations of immediate values
  * **Exercise:** Create different exit codes
  * **Extra:** Understanding PC (r15) and Link Register (r14)

* **Exercise 3: First Calculations**
  * Simple arithmetic operations
  * **Concepts covered:** ADD, SUB instructions with immediate and register operands
  * **Extra:** Understanding barrel shifter operations (LSL, LSR)

**Phase 2: Memory and Data**
* **Exercise 1: Data Section**
  * Define and use static data
  * **Concepts covered:** `.data` section, `LDR`, `STR`, address modes
  * **Focus:** Understanding ARM's load/store architecture

* **Exercise 2: Addressing Modes**
  * Different ways to access memory
  * **Concepts covered:** Pre/post indexing, write-back, scaled register offset
  * Example: `LDR r0, [r1, r2, LSL #2]`

* **Exercise 3: Stack Operations**
  * Using the stack for temporary storage
  * **Concepts covered:** `PUSH`, `POP`, multiple register transfer (`STMFD`, `LDMFD`)

**Phase 3: Control Flow**
* **Exercise 1: Condition Codes**
  * Use ARM's condition flags
  * **Concepts covered:** CPSR flags (N,Z,C,V), conditional execution
  * Example: `MOVEQ`, `ADDNE`

* **Exercise 2: Branching**
  * Implement conditional code paths
  * **Concepts covered:** `B`, `BL`, condition codes with branches
  * Focus on ARMv7's branch prediction hints

* **Exercise 3: Compare and Test**
  * Different comparison operations
  * **Concepts covered:** `CMP`, `TST`, `TEQ`, relationship with CPSR

**Phase 4: Functions and ABI**
* **Exercise 1: AAPCS**
  * ARM Architecture Procedure Call Standard
  * **Concepts covered:** r0-r3 for arguments, r0 for return value
  * Stack frame maintenance

* **Exercise 2: Function Implementation**
  * Writing reusable functions
  * **Concepts covered:** Register preservation, stack frame setup
  * Using `PUSH {lr}` and `POP {pc}`

* **Exercise 3: Nested Functions**
  * Complex function interactions
  * **Concepts covered:** Stack maintenance, register saving conventions

**Phase 5: Optimization Techniques**
* **Exercise 1: Conditional Execution**
  * Replace branches with conditional instructions
  * **Concepts covered:** Using condition codes effectively
  * Performance implications

* **Exercise 2: Efficient Memory Access**
  * Optimize data access patterns
  * **Concepts covered:** Alignment, efficient addressing modes
  * Using `LDMIA` and `STMIA` effectively

* **Exercise 3: SIMD with NEON**
  * Basic vector operations
  * **Concepts covered:** NEON registers, basic SIMD instructions
  * Focus on performance-critical code

**Phase 6: System Integration**
* **Exercise 1: Linux System Calls**
  * Common syscall implementations
  * **Concepts covered:** System call numbers, parameter passing
  * Error handling

* **Exercise 2: C Integration**
  * Writing assembly functions for C
  * **Concepts covered:** AAPCS compliance, stack alignment
  * Debugging mixed code

* **Final Project**
  * Write a string manipulation library
  * Implement common functions (strlen, strcpy, strcmp)
  * Optimize using ARMv7 features
