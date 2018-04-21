### What's going on in `Mystery.sol`?

##### Answer:
There is a constructor and a default function in the contract. Variable `g` is gas. `calldatacopy` copies `calldatasize` bytes from calldata at position 0 to position `o_code` (which is the memory end). variable `retval` is the result of the function `call` on input and the address provided to constructor. If it threw/was out of gas (`retval` == 0), we jump to a bad memory destination. If it succeeded (`retval` == 1), we return the result.
