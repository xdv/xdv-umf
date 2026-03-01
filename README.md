# XDV Unified Memory Fabric
Version: 0.1.1
Status: active-split
Language: Dust Programming Language (DPL)

## Specification Alignment
Primary specification: XDV-013 in xdv-spec.

## Purpose
`xdv-umf` provides deterministic, domain-aware memory control for K/Q/Phi domains.
It enforces:
- memory contract validation,
- no-clone policy for Q and Phi state,
- coherence policy for Phi state,
- cross-domain transfer policy and atomicity gates,
- direct mapping isolation boundaries.

## Scope Implemented in 0.1.1
- K/Q/Phi-aware memory contracts (`create_memory_contract`, `validate_memory_contract`).
- Deterministic domain allocation path (`domain_alloc_contract`) with region-aware addressing.
- No-clone and coherence enforcement in protection validation.
- Transfer-policy controls for K<->Q, K<->Phi, and Q<->Phi bridge rules.
- Isolation check API for direct mapping rejection.
- Contract/isolation/transfer tests in `src/umf_tests.ds`.

## Public Surface
- Forge module: `XdvUmf`
- Implementation: `src/umf.ds`
- Interface profile: `src/umf_interface.ds`

Version APIs:
- `xdv_umf_interface_version_major/minor/patch`
- `xdv_umf_contract_api_version`
- `xdv_umf_isolation_api_version`
- `xdv_umf_transfer_api_version`

## Build
`cargo run --manifest-path dust/Cargo.toml -- check xdv-umf/src`

## Integration Notes
- `xdv-kernel` integration remains compatible via existing `xdv_umf_interface_version_*` exports.
- Existing wrapper APIs (`domain_alloc`, `alloc_qstate_memory`, `transfer_qstate`, etc.) remain available.
