# VHDL Counter Bug
This repository demonstrates a common error in VHDL: incorrect signal assignment in a concurrent statement.  The `buggy_counter.vhdl` file contains a VHDL counter with a subtle error that prevents the output from updating correctly. The corrected version is in `fixed_counter.vhdl`.

## Problem
The original code uses a concurrent signal assignment (`count_out <= count;`) to update the output port. While seemingly correct, this approach doesn't guarantee immediate reflection of changes in the `count` signal to the `count_out` port. This is a significant difference from sequential signal assignments that are performed within processes. The original code results in an incorrect output.

## Solution
The solution in `fixed_counter.vhdl` illustrates the correct approach. The concurrent signal assignment is retained but it now correctly updates the output port synchronously with changes to the internal signal. 

## Learning Points
*   Understanding the difference between concurrent and sequential signal assignments in VHDL is crucial for writing correct and efficient code.
*   Concurrent statements are best suited for combinational logic, whereas sequential statements (within processes) are essential for sequential logic. 
*   Careful consideration of how signals are updated and their visibility in different parts of the code helps prevent unexpected behavior.