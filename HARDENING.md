<!-- markdownlint-disable -->

# Hardening Report: CultureHQ--actions-yarn/v1.0.1

> This file was generated automatically by the hardening agent.

**Policy SHA:** `d636be7e43ef829af6e853da6b3c7566db9f72fe`

**Test Policy SHA:** `843adf9e4b8f85d0c08b27b9d0b09dd094b54702`

**Harden Agent Version:** `2`

Action **CultureHQ--actions-yarn/v1.0.1** was hardened automatically. 1 finding(s) were identified and resolved across 1 iteration(s).

## Findings Fixed

### unpinned-uses (severity: high)

The action.yml uses a Docker image reference with a mutable tag (`docker://culturehq/actions-yarn:latest`) instead of an immutable SHA digest. This means the action could silently pull a different (potentially malicious) image on each run if the upstream tag is updated or hijacked. The image reference should be pinned to a specific SHA digest, e.g. `docker://culturehq/actions-yarn@sha256:<64-hex-char-digest>`.

Locations:

- `action.yml:6`

## Iteration Notes

### Iteration 1

**Fixes applied:** unpinned-uses

**Notes:**

Pinned the Docker image reference in action.yml from the mutable `docker://culturehq/actions-yarn:latest` to the immutable digest `docker://culturehq/actions-yarn:latest@sha256:e434d9710bb71fb48999d1feedda97b24b2f2405b683a4a94d4dd7e08680435f`. The `docker://` scheme and `:latest` tag are preserved inline as required.

