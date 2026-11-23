# Post-deploy verification

- Production URL: https://israel-bright.github.io/cps5981-lab12/
- Approved release: v1.0.0
- Approved SHA-256: `c074d33cd933c46e69d854b9d2bc6ccb0aee462181c7c48b7088df4cc175d168`
- Checked at: 2026-11-23 02:28:32 UTC
- Run: https://github.com/Israel-Bright/cps5981-lab12/actions/runs/45098041834

| Check | Expected | Actual | Result |
|---|---|---|---|
| release.json version | `v1.0.0` | `v1.0.0` | PASS |
| release.json sha256 | `c074d33cd933c46e69d854b9d2bc6ccb0aee462181c7c48b7088df4cc175d168` | `c074d33cd933c46e69d854b9d2bc6ccb0aee462181c7c48b7088df4cc175d168` | PASS |
| live tarball sha256 | `c074d33cd933c46e69d854b9d2bc6ccb0aee462181c7c48b7088df4cc175d168` | `c074d33cd933c46e69d854b9d2bc6ccb0aee462181c7c48b7088df4cc175d168` | PASS |
| live file app.env | `e7a038d260559c5b` | `e7a038d260559c5b` | PASS |
| live file app.js | `012ba120d10008fc` | `012ba120d10008fc` | PASS |
| live file index.html | `b2333fc43ffa7b78` | `b2333fc43ffa7b78` | PASS |
| live file package-lock.json | `aa2b81a69d6bbfcd` | `aa2b81a69d6bbfcd` | PASS |
| live file package.json | `d42b49ec2ce9c667` | `d42b49ec2ce9c667` | PASS |
| live file styles.css | `469bf822750a7826` | `469bf822750a7826` | PASS |

**Result: production is serving the approved bytes**
