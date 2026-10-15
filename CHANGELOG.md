# Changelog

All notable changes to this project are documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]

### Added
- SECURITY.md with threat model and disclosure policy
- Dependency audit step in CI (`pip-audit`)
- Coverage floor enforced at 60% in CI
- Committed lockfile for reproducible installs

### Changed
- CI now fails on lint, typecheck, or test failures (removed `|| true`)

## [0.1.0] - 2026-09-01

### Added
- Initial release: autonomous agent marketplace integration
- Crypto wallet signing (EIP-191) with AES-256-GCM vault
- USDC ledger and audit chaining
- FastAPI service with typed Pydantic models
- Structured logging via structlog
- Unit and integration test suite
