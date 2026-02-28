# Architecture
XDV Unified Memory Fabric is structured in two layers:
1. Stable interface layer (src/umf_interface.ds)
2. Implementation layer (src/umf.ds)
Tests from the source sector are imported into src and can be mirrored into tests as independent suites over time.
