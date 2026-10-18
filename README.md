# lib-libz

sdkgen-generated zlib FFI bindings — generic ports plus the `c-linux-x86_64` adapters, under `handl-packages/generated/`.

Part of the `handl-lang` org split (ADR-0128). History is a `git subtree
split` of the platform monorepo's `generated/libz/` (via `c`).

## Layout

```text
src/        the .hnl sources
pkg.hnl     dependencies, when any: `{ deps: { <name>: "branch:<ref>" } }`
```

## Gate

```bash
HNL=../host-cli/target/debug/hnl scripts/hnl-gate.sh
```
