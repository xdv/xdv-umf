# Architecture

`xdv-umf` is organized as:
1. Stable interface surface (`src/umf_interface.ds`)
2. Domain-aware memory implementation (`src/umf.ds`)

## Core Enforcement Blocks
- Contract block:
  - `create_memory_contract(...)`
  - `validate_memory_contract(...)`
- Domain protection block:
  - K/Q/Phi protection validation with no-clone and coherence checks
- Isolation block:
  - `request_direct_mapping(...)` rejects cross-domain direct mapping
- Transfer policy block:
  - policy-gated cross-domain transfer with atomicity enforcement

## Determinism
Allocation and contract derivation are deterministic for identical inputs.
No randomized mapping/arbitration path is used in UMF.
