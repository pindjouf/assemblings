# Hello, Assembly!

***The goal was to write an empty program that exits with status code 0.***

Our first exercise in the series, here we make the `_start` label which is the memory address that points to the location in memory from where we'll start executing instructions, global.

We then declare our first section as the `.text` section, this is where all our instructions go.
Then we can start writing instructions under the `_start` label.
We first load the immediate value `1` into register `R7` which is a special register that holds our syscall values.

Then the actual exit happens at the `swi` instruction which stands for software interrupt, this is where our system call gets executed. That's when the OS looks for the value stored at `R0` to know what the exit code is, if we did not manually specify it, then it defaults back to `0` to signal a successful exit!
