# compliance.tf Homebrew tap

Homebrew formulae of [compliance.tf](https://compliance.tf).

```sh
brew install compliancetf/tap/ctfkit
```

| Formula | What it is |
|---------|------------|
| `ctfkit` | [ctfkit by compliance.tf](https://github.com/compliancetf/ctfkit): an analyzer runtime that turns Terraform and OpenTofu configuration, plans and module manifests into SARIF findings and an evidence receipt. |

The formula installs the newest ctfkit release; `brew upgrade ctfkit` moves to the next one.
For a reproducible CI job or image, install a pinned release archive instead
([install guide](https://github.com/compliancetf/ctfkit/blob/master/docs/install.md)).

## How the formula is updated

The formula installs the release archive for your platform (macOS or Linux, arm64 or x86_64) and
pins its SHA-256 from the release's `checksums.txt`. [scripts/update-formula.sh](scripts/update-formula.sh)
renders it. Before it pins an archive, it checks with `gh attestation verify` that the ctfkit
release workflow built that archive from the release tag.

The `update-formula` workflow runs the script daily, by hand, and when a ctfkit release asks for
it, and commits only a changed formula. Do not edit `Formula/ctfkit.rb` by hand.

## License

Apache-2.0
