# VGL — Verified Gossip Ledger

**A peer-to-peer value transfer protocol that doesn't need a global ledger.**

VGL is a complete rethinking of how decentralized payments can work. Instead of forcing every node to agree on a single global history (like Bitcoin or Ethereum), VGL uses **local verification**, **pairwise handshakes**, and **bridges between independent units(each got their own money processing)** to transfer value instantly, and with near-zero cost.

If you understand how the internet routes packets without a global list of every packet ever sent, you already understand VGL. It applies the same architecture to money.

---

## The Core Idea

**Bitcoin asked:** *"How do we get everyone to agree on a global ledger?"*

**VGL asks:** *"How do we know, locally, that this specific payment is valid?"*

The answer is simple:

1. Money exists as **cryptographic tags** that move from one person to the next.
2. The current holder of a tag is the **only** person who can verify its validity.
3. A ** handshake** system and while it locking the current holder, prevents double-spending, and transfers the tag atomically.
4. No global state. No mining. No blocks. No fees.

---

## How It Works (In most basic and simple case, simplifed)

1. **Alice** wants to pay **James** 5 coins.
2. Alice tells James: *"The last person I paid was Charlie. and i wanna give you 5 coins"*
3. James asks Charlie directly: *"Are you the last?"*
4. Charlie replies: *"Yes. I am"*
6. James asks *"well does alice have 5 coins"*
7. Charlie replies *"yes he has, now i would give you the money and while that i would be from LAST -> WAITING"*
8. james now gets both the 5 coins and the tag that says he is last who interacted with alice and remaining alice money
9. james then after conpleting and getting everything tells charlie *"now i am last"*
10. **charile is removes waiting tag and he is now tagless about alice. Transaction done.

**THIS IS OVER SIMPLIFED, THE DETAILS OF HOW THIS ACTUALLY WORKS AND HOW IT DOESN'T TRUST CHARLIE IS IN THE PAPER**

---

## Architecture Overview
<img width="817" height="390" alt="1000014274" src="https://github.com/user-attachments/assets/56c83357-67b9-4fc6-946d-5e9245f4deba" />

---

## Key Innovations

| Feature | What It Solves | How |
| :--- | :--- | :--- |
| **WAITING Handshake** | Double-spending | Local mutual exclusion (3-way handshake for money) |
| **Double-Check Protocol** | Fraud / lying | Receiver independently asks the claimed predecessor for signed confirmation |
| **T-Nodes** | Cross-G-Node payments | Ephemeral, trustless bridges that dissolve after use |
| **PPOs** | Node failure | Backup E-Nodes with operation counters for automatic recovery |
| **Pyramid PoW** | Sybil resistance | Verifiable Delay Function (VDF) using Newton's forward differences |
| **No Global State** | Scalability, privacy | Each G-Node stores only its own transactions |

---

## Comparison vs. Bitcoin

| | Bitcoin | VGL |
| :--- | :--- | :--- |
| **Consensus** | Global (PoW) | Local (handshake) |
| **Finality** | ~60 minutes | Milliseconds |
| **Fees** | $1–$50+ | Near-zero |
| **Energy** | 100+ TWh/year | Negligible |
| **Scalability** | ~7 TPS | Unlimited (each G-Node processes independently) |
| **Privacy** | Pseudonymous (traceable) | High (no global view) |
| **Auditability** | Full global ledger | None by design |

---

## The Vision

VGL is not a blockchain. It is not a DAG. It is a **completely new category** of payment network:

> **VGL is to blockchain what the internet is to a single company owning every router and recording every packet in a global database.**

---

## Status

📄 **Whitepaper:** incomplete

🚀 **Production Implementation:** Not yet started  

📢 **Seeking:** people who are interested to learn and talk about it

---

## Contact & Links

- **GitHub:** [WeDu-official](https://github.com/WeDu-official)
- **discord server** https://discord.gg/zVDdFvwq4
- **Paper:** Is still under work
