# Interface Contract
Project: XDV Unified Memory Fabric
Specification: XDV-013
Forge: XdvUmf

## Versioning
- Interface version: 0.1.0
- Contract API version: 1
- Isolation API version: 1
- Transfer API version: 1
- Stability tier: frozen_normative

## Contract Rules
- Memory allocation and transfer decisions must be deterministic.
- Q and Phi state allocations must enforce no-clone policy.
- Phi state allocations must enforce coherence policy.
- Cross-domain transfers require explicit policy flags and atomicity for cross-domain paths.
- Direct cross-domain memory mapping is isolation-violating by contract.

## Public Files
- `src/umf.ds`
- `src/umf_interface.ds`

## Key Public APIs
- `create_memory_contract(...)`
- `validate_memory_contract(...)`
- `domain_alloc_contract(...)`
- `validate_domain_protection(...)`
- `transfer_state(...)`
- `transfer_qstate_with_policy(...)`
- `transfer_phi_state_with_policy(...)`
- `request_direct_mapping(...)`

## Stable Version APIs
- `xdv_umf_interface_version_major()`
- `xdv_umf_interface_version_minor()`
- `xdv_umf_interface_version_patch()`
- `xdv_umf_contract_api_version()`
- `xdv_umf_isolation_api_version()`
- `xdv_umf_transfer_api_version()`
