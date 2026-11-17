# Ethereum L1 Strawmap — Simple Guide

> **Source:** [strawmap.org](https://strawmap.org) (snapshot updated **Nov 2, 2026**)  
> **Maintained by:** EF Protocol / EF Architecture (Justin, Thomas, Toni, Vitalik)  
> **Canvas draft:** [diagram.excalidraw](./diagram.excalidraw)

---

## 1. What is the Strawmap?

**Strawmap** = **Strawman** + **Roadmap**.

It is a draft visual map of where Ethereum's Layer 1 (L1) protocol could go over the next several years (through **2029–2030+**). Unlike short-term trackers that only look 1–2 upgrades ahead, the Strawmap puts the long-term vision on one page so researchers and developers can see how upgrades connect.

> **Important:** It is a **conversation starter**, not a guaranteed schedule or official mandate.

---

## 2. The 5 Big Goals ("North Stars")

Everything on the map flows toward **5 final goals** on the right side:

| North Star | Layer | What it means in plain English |
|---|---|---|
| **Fast L1** | Consensus (CL) | Transactions get included and finalized in **seconds** (instead of ~13 minutes). |
| **Teragas L2** | Data (DL) | **1 Gbyte/sec** of data capacity (~10M TPS for Layer 2 rollups). |
| **Post-Quantum L1** | Cross-Layer | Upgrade signatures, proofs, and data sampling to **hash-based crypto** so quantum computers cannot break Ethereum. |
| **Gigagas L1** | Execution (EL) | **1 Ggas/sec** (~10K TPS directly on L1) powered by zkEVMs and real-time proving. |
| **Private L1** | Execution (EL) | Built-in **shielded transfers** so privacy works natively on Ethereum L1. |

---

## 3. How to Read the Map

### Time Moves Left → Right (Hard Forks)
Upgrades are grouped into roughly **6-month network upgrades (forks)**:

- **Glamsterdam (`G*`, ~Jan 2027)** → **Hegotá (`H*`, ~2027)** → **`I*` (~2028)** → **`J*` (~2028–29)** → **`K*` (~2029)** → **`L*` (~2029–30)** → **Longer term** → **North Stars**
- Named forks (`Glamsterdam`, `Hegotá`) are near-term and concrete; star names (`I*`, `J*`, `K*`, `L*`) are placeholders for future forks.

### Three Horizontal Layers (Top → Bottom)
1. **Consensus Layer (CL — Orange):** How validators agree on blocks and finalize the chain (slots, finality, validator roles, specs, proofs, quantum safety).
2. **Data Layer (DL — Green):** How blob data for rollups is stored, sampled, and scaled.
3. **Execution Layer (EL — Blue):** How transactions, gas, EVM state, privacy, and zkEVM proving work.
4. **Cross-Layer (Purple seam):** Shared post-quantum proving (`leanVM`) connecting CL, DL, and EL.

### Colors, Badges & Symbols

| Visual | Meaning |
|---|---|
| **Dark solid box** | **Headliner** — the main flagship upgrade of that fork (usually 1 CL + 1 EL per fork). |
| **Medium colored box** | **Onchain upgrade** — changes Ethereum's protocol rules directly. |
| **Grey box** | **Offchain upgrade** — client, networking, or spec improvements that don't need a hard fork rule change. |
| **Black box with ★** | **North Star** — one of the 5 long-term destination goals. |
| **`SFI` / `CFI` / `EIP`** | **Status badge:** *Scheduled For Inclusion* (`SFI`), *Considered For Inclusion* (`CFI`), or linked `EIP` proposal. |
| **⚛** | **Post-quantum** cryptography / Lean Ethereum upgrade. |
| **🤔** | **Uncertain** — might change or never ship. |
| **Arrows (→)** | **Throughlines** — natural progressions (not strict hard dependencies). |

---

## 4. What Happens in Each Layer? (Simple Walkthrough)

### Consensus Layer (Orange) — *"Make L1 fast, simple, and quantum-safe"*
- **Near term (`Glamsterdam` & `Hegotá`):**
  - **ePBS** (`SFI`): Separates block proposers from block builders inside the protocol.
  - **FOCIL** (`SFI`): Improves censorship resistance by letting committees enforce transaction inclusion.
  - **Fast confirmation** & **Post-quantum registrations**: Faster UX confirmations and early validator setup for quantum-safe keys.
- **Medium term (`I*` – `J*`):**
  - **Decoupled consensus** & **Quick slots**: Separates slot timing from finality to unlock faster blocks.
  - **leanXMSS PQ attestations**: Quantum-safe validator signatures.
  - **leanCL in Lean 4**: Formal mathematical specification of the consensus state machine.
- **Longer term (`K*` – `L*`+):**
  - **Slot duration decreases** + **1-round finality** → **Fast L1 (finality in seconds)**.
  - **Real-time `cl-asm` proofs** enable **secret proposers**, **51% attack auto-recovery**, and a **CL-enshrined shielded pool**.

### Data Layer (Green) — *"Scale rollup data to 1 GB/sec"*
- **Near term:** **Sparse blobpool** (`SFI`) and **cell-level deltas** (`SFI`) make propagating blob data much lighter.
- **Medium term (`I*` – `J*`):** **Distributed blob reconstruction** and **leanDA PQ sampling** (quantum-safe data availability sampling).
- **Longer term:** Continuous **data availability increases**, **remove blob transactions**, **blob streaming** → **Teragas L2 (1 Gbyte/sec)**.

### Execution Layer (Blue) — *"Scale L1 to 10K TPS with zkEVMs & native privacy"*
- **Near term (`Glamsterdam` & `Hegotá`):**
  - **BALs** (*Block-Level Access Lists*, `SFI`): Pre-declares what state a block touches for parallel execution.
  - **Frame transactions** (`SFI`): Flexible next-gen transaction format (paving the way for quantum-safe & private transactions).
  - **Gas repricings** (`Glamsterdam repricing`, `data repricing`) and **`evm-asm` / `optional proofs`** to prepare the EVM for ZK proving.
- **Medium term (`I*` – `J*`):**
  - **Partitioned binary tree** (cleaner state layout), **multidimensional pricing**, **payload sampling**, **leanSPHINCS** (PQ transactions), and **leanPCS frames** (privacy).
- **Longer term (`K*` – `L*`+):**
  - **Mandatory 1-of-1 proofs** (every block proven by a zkEVM) and **native rollups** → **Gigagas L1 (1 Ggas/sec)**.
  - **Wormholes** & **encrypted mempool** → **Private L1 (shielded transfers)**.

---

## 5. Summary in One Sentence

The Strawmap charts Ethereum's path over ~7 forks from **Glamsterdam (2027)** to **2030+** toward five concrete goals: **finality in seconds**, **10K TPS on L1**, **10M TPS on L2**, **post-quantum security**, and **native L1 privacy**.
