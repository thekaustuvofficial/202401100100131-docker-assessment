# FestPass Docker & Container Security - CA-2

- **Name:** Kaustuv
- **REGNO:** 202401100100131
- **PORT:** 8031
- **Docker Hub username:** mrsupreme
- **Docker Hub repository:** https://hub.docker.com/r/mrsupreme/fest-backend
- **GitHub repository:** https://github.com/thekaustuvofficial/202401100100131-docker-assessment

## AI tools used
- Claude (Anthropic): generated the Dockerfiles, compose.yaml and command sequences, and helped debug errors (cosign segfault, prompt/terminal setup). I ran every command myself on my own machine.

## Digest of 1.0.0 as pushed to Docker Hub
sha256:5e20889b924df2cfa353873a0f6f7b1b4e87b042a633fb2b0b170e4b7802559d

## Vulnerability before/after

| Image | Base image | CRITICAL | HIGH | Size |
|-------|------------|----------|------|------|
| fest-backend:0.1 (before) | python:3.9 | $B_CRIT | $B_HIGH | $SIZE01 |
| fest-backend:0.2 (after) | $BASE | $A_CRIT | $A_HIGH | $SIZE02 |

Scan command: trivy image --scanners vuln --severity CRITICAL,HIGH. The gate command
trivy image --severity CRITICAL --ignore-unfixed --exit-code 1 fest-backend:0.2 exits with code 0.

## Release signing
- 1.0.0 is signed with cosign (by digest) and verifies with cosign.pub.
- 1.0.1 is intentionally unsigned and is rejected by cosign verify.

## Steps not completed
- None
