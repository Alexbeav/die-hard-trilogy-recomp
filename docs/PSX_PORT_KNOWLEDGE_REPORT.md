# Die Hard Trilogy knowledge report

- Date: 2026-08-31
- Retail identity: USA NTSC-U `SLUS-00119`
- Architecture lane: source-only owned-input setup host
- Release target: Windows x64, version `0.3.4`
- License boundary: portfolio files use GPL-3.0-only; dependencies keep their licenses

## Current state

The operator confirmed gameplay in the private promoted package. This meets
the `bootstrap_verified` boundary. The source-only Windows package builds
locally. Exact-package setup, startup, and remote-byte gates remain open.

## Release controls

- Framework: afe9ab299aab0eeba1cc31f81bc4baf4e7fb2ab7
- recomp-ui: 4eda65430a431e5685ae0c515ebcd912c7843bff
- RetComM Studio: 249422969c1c59ac2a1f8aa2299e876a7133998e
- Distribution: owned input only
- Platform claim: Windows x64 only
- Deferred work: Linux x64, macOS ARM64, and macOS x64 CI jobs

## Open gates

1. Complete exact-package setup and a 10-second startup.
2. Run the regional and title-risk canaries from exact ZIPs.
3. Audit every downloaded private draft.
4. Bind publication authorization to the exact release manifest.

## Corpus consulted

The release work uses PSX-PUB-004, PSX-PUB-006, PSX-WIN-004,
PSX-WIN-005, PSX-WIN-006, and PSX-PUB-011.

## v0.3.4 setup correction

The source now uses `Die_Hard_Trilogy_Recompiled` as the only setup executable name. The batch source
gate passes. The exact-ZIP automatic-relaunch canary and remote release audit
remain open. Public `v0.3.0` remains unchanged.

## 2026-09-02 media identity finding

Canonical multi-BIN setup is blocked. The public configuration supports USA
Rev 1 `SLUS-00119` and stores the merged whole-disc digest, but the verifier
hashes the first BIN named by a CUE. The owned canonical Track 01 identity is
114,928,128 bytes, MD5 `07fb588670cf9d80ec40f1bd52620146`, and SHA-1
`2d24572e92415e09c37b68c83ba8b8947aee1ce4`. Close this gate only after an
exact-package canonical multi-BIN test passes. See `PSX-PUB-020`, `FAIL-115`,
and `_runs/knowledge/reviews/2026-09-02-disc-verification-wrong-dump.md`.
