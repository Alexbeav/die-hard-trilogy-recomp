# Development log

## 2026-09-01 — setup executable-name parity

The public `v0.3.0` source used different CMake and setup-relaunch executable
names. The corrected source uses `Die_Hard_Trilogy_Recompiled` in all three title-owned paths.
`Test-SetupExecutableNameParity.ps1` passes. Exact-ZIP automatic relaunch is
still required before release.

## 2026-09-02 — canonical multi-BIN verification failure

The mandatory corpus check found no existing exact match. The consult-test-return
loop then reviewed the release verifier and hashed the owned merged image only
through Track 02 `INDEX 00`. The public configuration supports USA Rev 1
`SLUS-00119`. It stores the merged 557,503,968-byte image identity while its
comment calls the values Track 01 digests. A standard CUE makes the verifier
hash the real 114,928,128-byte Track 01 file instead. Its MD5 is
`07fb588670cf9d80ec40f1bd52620146` and its SHA-1 is
`2d24572e92415e09c37b68c83ba8b8947aee1ce4`.

The corrected package accepted the canonical Rev 1 Track 01 and the original
merged CUE on Pegasus. It generated, rebuilt, launched through the setup helper,
and exited cleanly. The first package included two non-SDK scripts with a
developer path. Packaging revision `r2` removes only those files. Shared
records: `PSX-PUB-020`, `FAIL-115`, `FAIL-104`, and `PSX-PUB-016`.
