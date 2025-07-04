# 1. _afterTokenTransfer function 

# 2. ERC20Burnable 

# 3. Arithmetic error

# 4. Decimal places

# 5. Reentrancy Attacks

# 6. Access control

# 7. is there are problem if a txn is intercepted on the pool

# 8. Token Vulnerabilities

## 🔁 **I. Rebasing Tokens**

**Definition:** Tokens that **automatically adjust their total supply** (increase or decrease) to maintain a **target price** or **peg**.

**🔧 How It Works:**

* Instead of changing the token **price**, the protocol changes the **number of tokens** in your wallet.
* The value of your holdings stays the same, but the number of tokens increases or decreases.
* Common in **elastic supply tokens** like **Ampleforth (AMPL)**.

**🔄 Example:**

* You hold **100 AMPL**.
* If the price of AMPL is above the target (say \$1.05), the protocol **rebases** by increasing supply: now you have **110 AMPL** (but each is worth slightly less).
* If it's below \$1.00, you might end up with **90 AMPL**.

***🧠 Use Case:***

* Trying to create a **stablecoin** or **price-targeting token** without using collateral or reserves.

---

## 📈 **II. Inflationary Tokens**

**Definition:** Tokens that **increase in total supply** over time, usually through mechanisms like **staking rewards**, **mining**, or **yield farming**.

### 🔧 How It Works:

* New tokens are constantly minted and distributed.
* Token supply grows over time, causing **inflation**.
* Often used to **incentivize participation** (e.g., securing a network, providing liquidity).

### 🔄 Example:

* Ethereum (pre-merge) was inflationary: new ETH was issued to miners.
* Many DeFi protocols (like **Aave**, **Sushi**) have inflationary models for governance token rewards.

### ⚠️ Risk:

* If demand doesn’t keep up with supply growth, token price can go down.

---

## 📉 **III. Deflationary Tokens**

**Definition:** Tokens that **decrease in total supply** over time, usually by **burning tokens**.

### 🔧 How It Works:

* A portion of tokens is permanently destroyed (burned) on every transfer or periodically.
* This reduces circulating supply, aiming to make tokens more scarce (and potentially more valuable).

### 🔄 Example:

* **Shiba Inu (SHIB)** and **Safemoon** burn tokens on each transaction.
* Some protocols use **buy-and-burn** mechanisms (e.g., Uniswap fee burning).

### ✅ Use Case:

* Encouraging long-term holding by simulating scarcity.

---

## 💸 **IV. Tokens with Fee-on-Transfer**

**Definition:** Tokens that **charge a fee** every time they are transferred.

**🔧 How It Works:**

* A percentage (e.g., 1% to 10%) of the transferred amount is taken as a **fee**.
* Fee can be:

  * **Burned** (reducing supply),
  * **Redistributed** to holders (reflections),
  * **Sent to a treasury** or liquidity pool.

**🔄 Example:**

* **Safemoon**: 10% fee — 5% goes to holders, 5% to liquidity.
* **Reflect.finance (RFI)** uses **reflections**: rewards distributed to holders without staking.

**⚠️ Consideration:**

* Can break some DeFi protocols or DEXs that assume transfer amounts equal expected amounts (e.g., `transferFrom()` fails due to reduced amount).

---

**🧠 Summary Table**

| Type               | Supply Behavior   | Goal                         | Example              |
| ------------------ | ----------------- | ---------------------------- | -------------------- |
| Rebasing Token     | Expands/contracts | Peg to price                 | Ampleforth (AMPL)    |
| Inflationary Token | Increases         | Incentives for participation | Ethereum (pre-merge) |
| Deflationary Token | Decreases         | Increase scarcity            | SHIB, Safemoon       |
| Fee-on-Transfer    | Charged per tx    | Burn, redistribute, or fund  | Safemoon, RFI        |

# 9. Chain Interoperability

# 10. Common token decimal places
| Token         | Symbol | Decimals | Notes                              |
| ------------- | ------ | -------- | ---------------------------------- |
| USDT (Tether) | USDT   | 6        | Mirrors fiat precision             |
| USDC          | USDC   | 6        | Consistency with financial systems |
| DAI           | DAI    | 18       | Follows typical ERC-20 format      |
| WETH          | WETH   | 18       | Wrapped ETH (ERC-20 compliant)     |
| LINK          | LINK   | 18       | Chainlink native token             |
| UNI           | UNI    | 18       | Uniswap token                      |
| AAVE          | AAVE   | 18       | Aave protocol token                |
| Ethereum      | ETH    | 18       | Standard across ERC-20                     |
| Bitcoin       | BTC    | 8        | Smallest unit is 1 satoshi (10⁻⁸ BTC)      |
| Binance Coin  | BNB    | 18       | Same as Ethereum for consistency           |
| Solana        | SOL    | 9        | Smallest unit is a lamport                 |
| Avalanche     | AVAX   | 18       | Similar to Ethereum                        |
| Polygon       | MATIC  | 18       | Compatible with Ethereum tools             |
| Fantom        | FTM    | 18       | EVM-compatible chain                       |
| Tron          | TRX    | 6        | Lower decimal than Ethereum                |
| Cardano       | ADA    | 6        | Uses Lovelace (1 ADA = 1,000,000 Lovelace) |

