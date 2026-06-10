# Midnight ZK

[![Crates.io Version](https://img.shields.io/crates/v/midnight-proofs?label=midnight-proofs)](https://crates.io/crates/midnight-proofs)
[![Crates.io Version](https://img.shields.io/crates/v/midnight-curves?label=midnight-curves)](https://crates.io/crates/midnight-curves)
[![Crates.io Version](https://img.shields.io/crates/v/midnight-circuits?label=midnight-circuits)](https://crates.io/crates/midnight-circuits)
[![Crates.io Version](https://img.shields.io/crates/v/midnight-zk-stdlib?label=midnight-zk-stdlib)](https://crates.io/crates/midnight-zk-stdlib)

Welcome to the core repository for **Midnight's** proof system. This repository houses the foundational cryptographic implementations and the comprehensive tooling required to design, construct, and manage zero-knowledge circuits for the Midnight network.

## Project Architecture

The codebase is modularized into several key components to facilitate the ZK workflow:

- `curves`: Provides the essential elliptic curve cryptography, specifically featuring implementations for BLS12-381 and JubJub curves.
- `proofs`: Houses our Plonk proof system, which utilizes KZG commitments under the hood.
- `circuits`: A dedicated suite of tools and primitives for constructing zero-knowledge circuits.
- `aggregator`: Specialized utilities designed for aggregating `midnight-proofs`.
- `zk_stdlib`: A user-friendly, high-level standard library that streamlines the creation of ZK circuits by effectively abstracting the underlying `proofs` and `circuits` modules.

## Credits & Acknowledgments

The development of Midnight ZK is deeply rooted in the stellar work of the broader open-source cryptography community. We would like to extend our sincere gratitude to the creators and maintainers of the following outstanding projects:

- [`blstrs`](https://github.com/filecoin-project/blstrs) – Developed by the Filecoin Project
- [`jubjub`](https://github.com/zcash/jubjub) – Developed by the Zcash Project
- [`halo2curves`](https://github.com/privacy-scaling-explorations/halo2curves) (v0.8.0) – Developed by the Privacy Scaling Explorations (PSE) team
- [`halo2`](https://github.com/privacy-scaling-explorations/halo2) (v0.3.0) – Developed by the PSE team, which itself was originally adapted from the [Zcash Sapling proving system](https://github.com/zcash/halo2)

**Evolution of our codebase:**

In the early stages of this project, several of our components were maintained as direct forks:
- The `bls12_381` module (and its integrated `jubjub` implementation) began as forks of `blstrs` and `jubjub`.
- The `proofs` module was originally a fork of `halo2` (v0.3.0).

As Midnight has grown, our specific technical requirements have naturally led our codebase to diverge significantly from these upstream sources. Consequently, these components have matured into fully independent, specialized implementations rather than maintained forks. We remain incredibly thankful for the robust foundations these original projects provided.
