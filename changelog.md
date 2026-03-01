# Changelog

## 0.1.1 - XDV-013 Contract/Isolation Enforcement Milestone
- Replaced placeholder UMF logic with deterministic domain-aware memory contracts in `src/umf.ds`.
- Added K/Q/Phi protection validation enforcing:
  - no-clone policy for Q/Phi state,
  - coherence policy for Phi state,
  - cross-domain isolation boundaries.
- Added deterministic allocation path (`domain_alloc_contract`) with region-aware pointer derivation.
- Added transfer policy gates and atomicity checks for cross-domain transfers.
- Added direct-mapping isolation API (`request_direct_mapping`).
- Added concrete tests in `src/umf_tests.ds` for:
  - contract enforcement,
  - no-clone/coherence enforcement,
  - transfer-policy allow/deny paths,
  - isolation and contract validation behavior.
- Added namespaced interface-surface version methods in `src/umf_interface.ds`.

## 0.1.0 - Sector Split Baseline
- Created standalone project from `xdv-kernel/sector/xdv_umf`.
- Copied source module and tests into `src/`.
- Added stable interface file: `src/umf_interface.ds`.
- Added initial docs and interface contract.
- Added LICENSE copied from `xdv-os/LICENSE`.
