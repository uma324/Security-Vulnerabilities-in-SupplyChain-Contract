# Security-Vulnerabilities-in-SupplyChain-Contract
The provided contract has two significant security vulnerabilities:
1. Reentrancy Attack: The transferItem function does not properly handle reentrant calls, which can lead to unexpected behavior or loss of funds.
2. Unauthorized Access: The same address that owns the item is also allowed to transfer it without any additional validation
# Explanation of Security Enhancements
The rewritten transferItem function includes the following security enhancements:
# NonReentrant modifier
  - This ensures that once a transaction starts executing this function, it cannot be interrupted by another call to itself.
#	Zero-address attack prevention
  - The contract checks if the new owner is not address(0), which prevents attackers from sending funds to an empty account and then transferring ownership back to themselves.
#	Unauthorized access protection
- Additional validation ensures that the item's original owner cannot transfer it back to their own wallet, preventing unauthorized transfers.


