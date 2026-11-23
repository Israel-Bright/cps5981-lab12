# Independent verification and validation

Release v1.0.0, SHA-256 `c074d33cd933c46e69d854b9d2bc6ccb0aee462181c7c48b7088df4cc175d168`, repository https://github.com/Israel-Bright/cps5981-lab12

## Verification: ShipShield repository scan
| Item | Result |
|---|---|
| Security score | 100 |
| Compliance and trust score | 80 |
| Finding tracker | 22 open |
| Highest-severity finding | Medium · dompurify 3.2.4 · GHSA-39q2-94rc-95cp · CWE-783 |
| Ships in this release? | Yes: it is in the SBOM bound to my SHA-256 |

Evidence: shipshield.sarif

## Validation: CTOScore release-practice assessment
Score: 45 D, from 10% of the practice bank answered.

q07 — 3 (Managed): Source code is maintained in GitHub, and trusted pipeline changes were merged through PR #1. This rating also requires an active main-branch protection rule or ruleset.

q08 — 0 (Not in place): PR #1 records the changes, but no independent peer review before merge is documented.

q09 — 1 (Ad hoc): .github/workflows/secrets-scan.yml runs a blocking secret scan; run 45063595265 failed when it detected the exposed lab token. The full set of scans listed in this practice is not demonstrated on every change.

q10 — 2 (Defined): .github/workflows/deploy.yml deploys by version and digest after named approval. Run 45098041834, attempt 2, succeeded, and post-deploy.md records matching production bytes. Rollback within minutes has not been demonstrated.

q13 — 2 (Defined): config/app.env no longer contains the token, and DEPLOY_TOKEN is stored as a production environment secret. The secret scan blocks leaks, while .gitleaksignore documents the specific historical lab-token exception.

q15 — 2 (Defined): The release workflow produces release-sbom.json; release run 45068921503 provides the release evidence. ShipShield identified 22 open dependency findings, but ongoing monitoring and a patching SLA have not been demonstrated.

Evidence: ctoscore-assessment.pdf

## What each shows, and what neither shows
The ShipShield scan shows 22 open dependency findings for dompurify 3.2.4 despite displaying a Security score of 100 and a Compliance & Trust score of 80.
The CTOScore assessment shows a score of 45, grade D, based on the practices rated, covering 10% of the practice bank.
Neither tool proves that the application is correct, free of vulnerabilities, or suitable for its intended users.
