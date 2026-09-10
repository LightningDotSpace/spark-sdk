# Breez SDK - CLI Examples

Example CLI clients for the [Breez SDK](../../../../../README.md) in multiple languages.

## Source of Truth

The **[Rust CLI](../../../cli/)** (`crates/breez-sdk/cli/`) is the canonical implementation. All other language CLIs are ports that mirror its commands, arguments, and behavior.

Upstream `breez/spark-sdk` propagates Rust CLI changes to the language ports via a `sync-cli` GitHub Actions workflow. This DFX fork does not run that workflow (removed along with the other inherited language-binding/publish CI); port Rust CLI changes to the language CLIs manually if needed.

## Available Languages

| Language | Path | Status |
|----------|------|--------|
| [C#](langs/csharp/) | `langs/csharp/` | Active |
| [Flutter (Dart)](langs/flutter/) | `langs/flutter/` | Active |
| [Go](langs/golang/) | `langs/golang/` | Active |
| [Kotlin Multiplatform](langs/kotlin-multiplatform/) | `langs/kotlin-multiplatform/` | Active |
| [Python](langs/python/) | `langs/python/` | Active |
| [React Native](langs/react-native/) | `langs/react-native/` | Active |
| [Swift](langs/swift/) | `langs/swift/` | Active |
| [WASM (TypeScript)](langs/wasm/) | `langs/wasm/` | Active |

## Behavioral Tests

Shared end-to-end scenarios live in [`crates/breez-sdk/cli/tests/scenarios/`](../../../cli/tests/scenarios/): JSON files describing wallet flows as CLI commands plus expected output. They are shared verbatim across languages; each port gets a thin runner instead of ported tests. The Rust CLI runs them via `make cli-itest`; the WASM, Swift, and Kotlin ports run the same files via `make wasm-itest`, `make swift-itest`, and `make kotlin-itest`. See the [scenarios README](../../../cli/tests/scenarios/README.md) for the runner table, the schema, and the sync contract.

