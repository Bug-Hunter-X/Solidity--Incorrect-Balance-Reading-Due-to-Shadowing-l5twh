# Solidity Bug: Incorrect Balance Reading

This repository demonstrates a common yet subtle bug in Solidity smart contracts related to variable shadowing.  The `balanceOf` function in the original code incorrectly uses a local variable with the same name, instead of the intended storage variable, resulting in inaccurate balance reporting.

The solution provided corrects this by removing the local `balanceOf` variable declaration, ensuring that the contract's state variable is used.

## Bug:

The `bug.sol` file contains the buggy code.  The incorrect `balanceOf` function leads to unexpected behavior, potentially leading to security vulnerabilities.

## Solution:

The `bugSolution.sol` file provides the corrected code.  The bug is fixed by removing the local `balanceOf` variable, directly referencing the contract's state variable instead.

## How to reproduce

1. Compile and deploy both versions using a Solidity compiler like Remix or Hardhat.
2. Observe the differences in the return values from calling the `balanceOf` function.

## Lessons Learned

This example highlights the importance of careful variable naming and scope management in Solidity contracts. Shadowing of variables with the same name is one of the common causes for subtle issues, which could cause various problems in the application and it's usage.