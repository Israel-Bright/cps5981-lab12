# Provenance record

Release v1.0.0, artifact `cougar-advising.tar.gz`, SHA-256 `c074d33cd933c46e69d854b9d2bc6ccb0aee462181c7c48b7088df4cc175d168`
Checked by provenance-check run 45071572399: https://github.com/Israel-Bright/cps5981-lab12/actions/runs/45071572399

| Case | File | Expected | Result |
|---|---|---|---|
| The released bytes, builder constrained to release.yml | verify-pass.txt, verify-pass.json | verifies | PASS. Signed by https://github.com/Israel-Bright/cps5981-lab12/.github/workflows/release.yml@refs/heads/main |
| The same bytes plus one byte | verify-fail-tampered.txt | fails | Error: HTTP 404: Not Found |
| The right bytes, but demanding hotfix.yml as builder | verify-fail-wrong-builder.txt | fails | Error: verifying with issuer "sigstore.dev" |

attestation-bundle.jsonl is the signed attestation itself: anyone can check it with `gh attestation verify --bundle`.

## What this proves, and what it does not
Proves: The artifact matches the attested digest and comes from the specified release workflow and source commit.
Does not prove: The source code is correct, free of vulnerabilities, or built by an uncompromised builder.
