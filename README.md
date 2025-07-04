# 🛡️ Web3 Security Cheatsheet

![Solidity](https://img.shields.io/badge/Solidity-^0.8.20-blueviolet)
![Foundry](https://img.shields.io/badge/Foundry-%F0%9F%94%A5-red)
![Slither](https://img.shields.io/badge/Slither-Static_Analyzer-green)
![Hardhat](https://img.shields.io/badge/Hardhat-EVM_Yellow)
![Echidna](https://img.shields.io/badge/Echidna-Fuzzer-orange)
![MythX](https://img.shields.io/badge/MythX-Security_Scanner-lightgrey)
![Scribble](https://img.shields.io/badge/Scribble-Formal_Verification-blue)
![Status](https://img.shields.io/badge/Status-Active-brightgreen)
![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)

---

A curated collection of personal notes, code snippets, vulnerability patterns, and real-world exploit writeups from my journey as a smart contract auditor and Web3 security researcher.

This repo is actively maintained and serves as a reference for auditing, CTF solving, fuzzing, exploit reproduction, and secure smart contract development.

---

## 🗂️ Table of Contents

- [🛡️ Web3 Security Cheatsheet](#️-web3-security-cheatsheet)
  - [🗂️ Table of Contents](#️-table-of-contents)
  - [📖 Vulnerabilities](#-vulnerabilities)
  - [🛠 Audit Tools](#-audit-tools)
  - [📌 Secure Patterns](#-secure-patterns)
  - [💥 Exploit Replications](#-exploit-replications)
  - [⚙️ Gas Optimization Notes](#️-gas-optimization-notes)
  - [📚 Resources \& Learning](#-resources--learning)
  - [🧑‍💻 Contributions](#-contributions)
  - [📜 License](#-license)

---

## 📖 Vulnerabilities

Detailed notes on common Web3 and EVM smart contract vulnerabilities, including:
- Reentrancy
- Integer overflow/underflow
- Insecure delegatecall/use of `tx.origin`
- Oracle manipulation
- Flash loan abuse
- Unchecked return values
- Upgradeable contract pitfalls

Find them in [`/vulnerabilities`](./vulnerabilities)

---

## 🛠 Audit Tools

Usage and tips for:
- [Foundry](./tools/foundry.md)
- [Slither](./tools/slither.md)
- [Echidna](./tools/echidna.md)
- [MythX](./tools/mythx.md)
- [Scribble](./tools/scribble.md)

Includes config setups, commands, and examples for fuzzing and symbolic execution.

---

## 📌 Secure Patterns

A growing collection of secure Solidity coding patterns including:
- Checks-Effects-Interactions
- Pull payments
- Access control best practices
- Circuit breakers
- Safe upgradeable proxies

See [`/patterns`](./patterns)

---

## 💥 Exploit Replications

Reproductions and analysis of real-world Web3 hacks using Foundry, Hardhat or other tools:
- Curve reentrancy
- Nomad bridge failure
- Euler flash loan exploit
- Custom-built CTFs and puzzles

See [`/exploit-replications`](./exploit-replications)

---

## ⚙️ Gas Optimization Notes

Trade-offs and tips for reducing gas usage:
- Memory vs storage
- Constants vs state variables
- Short-circuit logic
- Packing variables
- Using `unchecked` safely

---

## 📚 Resources & Learning

Go-to materials I use to stay updated and sharpen my skills:
- Auditing checklists
- Secureum resources
- Ethernaut & Damn Vulnerable DeFi links
- Writeups and challenge sites

See [`/resources.md`](./resources.md)

---

## 🧑‍💻 Contributions

This is a personal learning project, but feel free to open issues or PRs with insights, fixes, or suggestions.

---

## 📜 License

This project is licensed under the MIT License — see the [LICENSE](./LICENSE) file for details.
