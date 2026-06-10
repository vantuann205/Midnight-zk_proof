<div align="center">

# Midnight ZK-Proofs Core

**The foundational zero-knowledge proof system powering the Midnight Network**

[![Midnight Proofs](https://img.shields.io/crates/v/midnight-proofs?label=midnight-proofs&style=flat-square)](https://crates.io/crates/midnight-proofs)
[![Midnight Curves](https://img.shields.io/crates/v/midnight-curves?label=midnight-curves&style=flat-square)](https://crates.io/crates/midnight-curves)
[![Midnight Circuits](https://img.shields.io/crates/v/midnight-circuits?label=midnight-circuits&style=flat-square)](https://crates.io/crates/midnight-circuits)
[![Midnight ZK Stdlib](https://img.shields.io/crates/v/midnight-zk-stdlib?label=midnight-zk-stdlib&style=flat-square)](https://crates.io/crates/midnight-zk-stdlib)

<p align="center">
  <i>Robust Cryptography • Scalable Proofs • Developer-Friendly Circuit Tooling</i>
</p>

</div>

---

## About This Repository

Welcome to the official repository for the **Midnight ZK** ecosystem. This monorepo is the heart of Midnight's privacy-preserving technology. It encapsulates a highly optimized, production-ready implementation of our zero-knowledge proof system, alongside a comprehensive suite of tools designed to make building, verifying, and aggregating ZK circuits as seamless as possible.

Whether you are a protocol core developer, a cryptography researcher, or an engineer building decentralized applications on Midnight, this repository provides the critical primitives required to unlock the full potential of programmable data protection.

---

## Architectural Overview

To ensure maximum maintainability, security, and modularity, the Midnight ZK stack is meticulously divided into several specialized crates. Each component serves a distinct and vital purpose in the lifecycle of a zero-knowledge proof:

### 1. `curves` — *The Cryptographic Foundation*
Elliptic curve cryptography is the absolute bedrock of modern ZK systems. This crate provides highly optimized, secure implementations of the specific mathematical curves utilized by the Midnight network:
* **BLS12-381**: A pairing-friendly curve that is essential for our polynomial commitment schemes.
* **JubJub**: A twisted Edwards curve built over the BLS12-381 scalar field, carefully chosen for efficient inside-circuit operations and cryptography.

### 2. `proofs` — *The Proving Engine*
This is the core mathematical engine of the repository. It implements a highly refined version of the **Plonk** proof system. To achieve optimal performance, succinctness, and fast verification times, this implementation is paired with **KZG (Kate-Zaverucha-Goldberg) polynomial commitments**. It handles the heavy lifting of generating and verifying the cryptographic proofs that guarantee both privacy and computational correctness.

### 3. `circuits` — *The Developer Toolkit*
Building custom ZK circuits from scratch can be notoriously complex. The `circuits` crate provides the low-level APIs, necessary abstractions, and specialized tooling required to construct robust and efficient zero-knowledge circuits. It acts as the crucial bridge connecting raw cryptographic mathematics with programmable logic.

### 4. `aggregator` — *Scaling Through Composition*
On-chain proof verification can become a bottleneck at scale. The `aggregator` toolkit solves this challenge by enabling the recursive aggregation of multiple individual `midnight-proofs` into a single, succinct master proof. This is a critical infrastructure component for achieving high transaction throughput and scalability across the Midnight ecosystem.

### 5. `zk_stdlib` — *The Standard Library*
Designed specifically with the end-user in mind, `zk_stdlib` provides a high-level abstraction layer. It wraps the deep complexities of both the `proofs` and `circuits` crates into an intuitive, developer-friendly standard library. If you are building applications that require zero-knowledge capabilities, this will be your primary entry point.

---

## Heritage & Acknowledgments

Midnight ZK does not exist in a vacuum—we stand on the shoulders of giants. The development of our proof system was profoundly inspired by, and originally bootstrapped from, several pioneering open-source projects in the applied cryptography space. 

We extend our deepest gratitude and respect to the brilliant teams, researchers, and open-source contributors behind the following libraries:

* **[`blstrs`](https://github.com/filecoin-project/blstrs)** – Crafted by the **Filecoin Project**.
* **[`jubjub`](https://github.com/zcash/jubjub)** – Pioneered by the **Zcash Project**.
* **[`halo2curves` (v0.8.0)](https://github.com/privacy-scaling-explorations/halo2curves)** & **[`halo2` (v0.3.0)](https://github.com/privacy-scaling-explorations/halo2)** – Developed by the **Privacy Scaling Explorations (PSE)** team (with `halo2` originally deriving its roots from the groundbreaking work on the [Zcash Sapling proving system](https://github.com/zcash/halo2)).

### The Evolution of Midnight ZK: From Forks to Native Implementations

In the project's infancy, pragmatic engineering dictated that we leverage existing, battle-tested codebases. Our initial `bls12_381` and `jubjub` modules started out as direct forks of the `blstrs` and `jubjub` repositories. Similarly, our core `proofs` engine began its life as a fork of PSE's `halo2` v0.3.0.

However, over months of relentless development, rigorous optimization, and alignment with Midnight's unique architectural and security requirements, our codebase has undergone a radical transformation. We have introduced bespoke features, custom performance optimizations, and Midnight-specific logic that now deeply separate our code from its upstream origins. 

Today, these components are **no longer maintained as forks**. They have matured into standalone, native implementations uniquely tailored for Midnight. While our development paths have diverged, the robust foundations laid by these original projects remain an indelible part of our history, and we remain continually thankful for the open-source ethos that made this possible.
