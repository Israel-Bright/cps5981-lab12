# Secret controls

Repository: https://github.com/Israel-Bright/cps5981-lab12

## 1. Platform controls are on
| Control | Evidence |
|---|---|
| Secret Protection (secret scanning) | screenshot in this folder |
| Push protection | screenshot in this folder |
| Blocking gitleaks check | secrets-scan run 45063595265 failed on the finding; the pull request run passed after revocation |

## 2. The finding
- gitleaks fingerprint: `fc41fc6fa156c12dfc79caf90aa90aedcfb0a530:config/app.env:generic-api-key:5`
- Where it was readable: The deployed website exposes the full fabricated token through /app.env. The release workflow’s “Load configuration” log also prints a token prefix.

## 3. The lifecycle
| Step | What was done |
|---|---|
| Externalized | Removed from `config/app.env` and from the build; it no longer ships in the artifact or the website |
| Scoped | Environment secret on `production`, readable only by a job in that environment, after a named approval |
| Rotated | New value stored 2026-11-22 |
| Audited | Every consumer: release.yml reads DEPLOY_TOKEN from config/app.env and logs its first 16 characters. build/build.sh copies the entire configuration file into the release archive, and deploy.yml publishes it on the website. hotfix.yml also calls this build script. Publishing and deployment use github.token, so rotating the fabricated DEPLOY_TOKEN would not disable those GitHub operations. Revocation is simulated for this lab because the supplied token is fabricated. In a real system, I would revoke the exposed token at its issuer before adding an ignore entry. |
| Revoked | Yes, revoked before anything else. Only then was the fingerprint added to `.gitleaksignore` |

## 4. Why deleting the line was not enough
(Your words: the commit, the log and the website were public. What ends the exposure?)
