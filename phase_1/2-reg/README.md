# Register Basics and function calls

***The goal was to play with immediate values and registers, and understand the Program counter register `(R15)` and the Link register `R14`.***
In my implementation I learned how to print to stdout and use one *function* to do al the work, I simply set up the registers to point or store different values before each call and I now know that the program counter is a constant pointer to the next instruction and that's why I used the `bl` instruction to store the address of the next instruction in the Link register and I then use that value at the exit of the function to come back and do it all over again until we're done with the program!

Here it is in more technical terms:

1. **Program Counter (R15) and Link Register (R14) Usage**
   - Used `bl` (Branch with Link) to implement function calls
   - The `bl` instruction automatically stores the return address in LR
   - `mov pc, lr` at function exit restores program flow

2. **Register Parameter Passing**
   - R0: File descriptor (stdout = 1)
   - R1: String address (loaded using ldr aka `const char *buf`)
   - R2: String length (loaded and dereferenced using ldr/ldrb. Redundant I know but I think it's cool)
   - R7: System call number

3. **Function Design Pattern**
   - Created reusable `print` function
   - Preserves register state by reinitializing R0
   - Demonstrates proper function return mechanism
