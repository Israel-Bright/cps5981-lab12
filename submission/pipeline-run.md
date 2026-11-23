# Pipeline runs

Repository: https://github.com/Israel-Bright/cps5981-lab12
Pull request: https://github.com/Israel-Bright/cps5981-lab12/pull/1
Failing secrets-scan on the branch: https://github.com/Israel-Bright/cps5981-lab12/actions/runs/45063595265

| Run | Workflow | Run ID | URL | What it shows |
|---|---|---|---|---|
| A | release (starter) | 44611854566 | https://github.com/Israel-Bright/cps5981-lab12/actions/runs/44611854566 | Released as "latest build from main"; no hash, no version; token printed in the log |
| H | hotfix (starter) | 45053896813 | https://github.com/Israel-Bright/cps5981-lab12/actions/runs/45053896813 | Yes, same name, different bytes; built from an unpushed commit; deployed with no review |
| B | release (trusted) | 45068921503 | https://github.com/Israel-Bright/cps5981-lab12/actions/runs/45068921503 | v1.0.0 from 6669de9; provenance and SBOM attested; immutable |
| P | provenance-check | 45071572399 | https://github.com/Israel-Bright/cps5981-lab12/actions/runs/45071572399 | PASS for the released bytes; FAIL for one changed byte; FAIL for the wrong builder |
| C | deploy | 45098041834 | https://github.com/Israel-Bright/cps5981-lab12/actions/runs/45098041834 | Approved by Israel-Bright; post-deploy PASS: production serves the approved bytes |

The digest that ties B, P and C together: `c074d33cd933c46e69d854b9d2bc6ccb0aee462181c7c48b7088df4cc175d168`
Production: https://israel-bright.github.io/cps5981-lab12/
