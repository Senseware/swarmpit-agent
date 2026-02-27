# Changelog

This changelog tracks Senseware-specific deltas from upstream `swarmpit/agent`.

## 2026-02-27

### Fork Baseline and Compatibility Update

- Added Senseware fork documentation and ownership context in `README.md`.
- Added default Docker API target `1.52` with runtime env fallback when `DOCKER_API_VERSION` is unset.
- Exposed configured Docker API version in agent `/info` payload.
- Updated build defaults to current toolchain baseline:
  - Docker build stage image updated to `golang:1.22`
  - `go` directive updated to `1.22`
- Added GitHub Actions workflow for test/build/publish with GHCR image targets.
- Updated image references and badges/links to Senseware repositories and GHCR path.
- Updated legacy deploy script defaults to `senseware/swarmpit-agent`.
