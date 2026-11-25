# lib-libz

codegen-generated zlib FFI bindings — generic ports plus the
`c-linux-x86_64` adapters, emitted under `handl-packages/generated/` (a
gitignored build artifact).

## Layout

| path | role |
| --- | --- |
| `specs/libz.sdkgen.yaml` | committed sdkgen input narrowing the zlib.h surface |
| `scripts/hnl-gate.sh` | the gate — regenerates bindings then typechecks/lints/tests |
| `handl-packages/generated/` | build artifact — gitignored |
| `pkg.hnl` | manifest — metadata only; the repo ships no `src/` modules |

## Contract

- Generated `.hnl` bindings for zlib, consumed through `.handl.toml`
  path deps; output is not committed.

## Regenerate

```bash
hnl codegen c /usr/include/zlib.h \
  --output handl-packages/generated/libz \
  --config specs/libz.sdkgen.yaml
```

Needs libclang — set `LIBCLANG_PATH` if the loader cannot find it.

## Verification

```bash
HNL=../host-cli/target/debug/hnl scripts/hnl-gate.sh
```

## License

MIT.

<!-- myco:agent-awareness -->

## Agent awareness

- Session start / any work discussion: run `myco status --prompt`
  before proposing next steps — know the board first.
- User describes new work → offer to capture it (`myco todo add`,
  `issue new`, `proposal new`). Don't wait to be asked.
- Picking up a task: `myco resume <ID>` is the briefing.
- Wrapping up: `myco handoff <ID>` anything resumable; keep statuses
  honest (claimed → in-progress → blocked/done).

<!-- /myco:agent-awareness -->
