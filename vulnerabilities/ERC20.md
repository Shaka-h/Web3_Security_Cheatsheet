### Fees on transfer

### Rebasing tokens

### _afterTokenTransfer function 

### ERC20Burnable 
Extension of {ERC20} that allows token holders to destroy both their own
 * tokens and those that they have an allowance for, in a way that can be
 * recognized off-chain (via event analysis).

### Arithmetic error
Great question. The behavior of arithmetic operations (like addition, subtraction, multiplication) in Solidity depends heavily on the **Solidity version** you’re using. Here's a breakdown by version:

---

##### ✅ **Solidity < 0.8.0** (e.g. 0.7.x and below)

* **Arithmetic operations do NOT have built-in overflow/underflow protection.**
* **Silent wraparound occurs**:

  * `uint8 x = 255; x + 1` becomes `0` (wraps around).
  * No error is thrown.
* Developers had to use libraries like [`SafeMath`](https://docs.openzeppelin.com/contracts/2.x/api/math#SafeMath) to manually protect against this.

🔒 Example:

```solidity
// Solidity 0.7.x
uint256 x = 2**256 - 1;
uint256 y = x + 1; // No error — y becomes 0 due to overflow.
```

---

##### ✅ **Solidity ≥ 0.8.0** (e.g. 0.8.0 and above)

* **Overflow and underflow checks are built-in for all arithmetic operations** on `uint` and `int`.
* **Throws a `Panic(uint256)` error with error code 0x11 (overflow) or 0x12 (underflow)** if it occurs.
* No need for `SafeMath` in most cases anymore.

🔒 Example:

```solidity
// Solidity 0.8.x
uint256 x = type(uint256).max;
uint256 y = x + 1; // Reverts with overflow error.
```

---

##### ✅ Summary Table

| Solidity Version | Overflow/Underflow Protection | Wraparound Behavior | Reverts on Overflow |
| ---------------- | ----------------------------- | ------------------- | ------------------- |
| `< 0.8.0`        | ❌ Manual via `SafeMath`       | ✅ Yes               | ❌ No                |
| `>= 0.8.0`       | ✅ Built-in                    | ❌ No                | ✅ Yes               |

---

##### 🛠 When Might You *Not* Want Checks?

* **Unchecked blocks** in `>=0.8.0` allow you to disable checks for gas optimization:

```solidity
unchecked {
    x = x + 1; // No overflow check
}
```

---

### Decimal places
WBTC (8 decimals), USDC (6 decimals)

### Reentrancy Attacks
Prevention Strategies
- Never call external contracts (like transfer()) before updating internal state.

- Use checks-effects-interactions pattern.

- Consider using reentrancy guards.

- Avoid trusting tokens with hooks (e.g. ERC777) unless absolutely needed.

