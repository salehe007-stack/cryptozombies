# CryptoZombies — Solidity Smart Contract Course

Completed all 6 lessons building a zombie battle game on Ethereum. Each lesson layered new Solidity concepts onto a single growing codebase.

## What I built

A multi-contract DApp where users create zombies with unique DNA, feed on other contracts (CryptoKitties), battle other players, and trade zombies as ERC721 tokens — with payments, access control, and security hardening throughout.

## Key concepts applied

- **Contract architecture** — inheritance chains, imports, interfaces to interact with external contracts, modifiers for reusable access control
- **Data structures** — mappings, structs with packed storage (`uint16`/`uint32` for gas savings), dynamic arrays, storage vs memory pointers
- **ERC721 token standard** — `balanceOf`, `ownerOf`, `transferFrom`, approve pattern, `Transfer`/`Approval` events
- **Security** — Ownable pattern (OpenZeppelin), SafeMath for overflow protection, visibility review to close public attack surfaces, `require` guards on every external function
- **Payments** — `payable` functions, `msg.value`, ETH withdrawal with `transfer`, updatable fee structures
- **On-chain logic** — pseudo-random number generation (`keccak256` + nonce), cooldown timers with block timestamps, if/else battle mechanics with win/loss tracking

## Contract structure

```
ZombieFactory (base) → ZombieFeeding → ZombieHelper → ZombieAttack → ZombieOwnership
         ↑                                                                    ↑
      Ownable                                                              ERC721
```

Each contract inherits from the one before it, adding a layer of functionality.

## What's next

Moving to Foundry — building Escrow, PaymentSplitter, and Voting contracts from spec with full test suites.
