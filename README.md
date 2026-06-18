# spore-host-plugin-tailscale

[![Go Report Card](https://goreportcard.com/badge/github.com/spore-host/spore-host-plugin-tailscale)](https://goreportcard.com/report/github.com/spore-host/spore-host-plugin-tailscale)
[![codecov](https://codecov.io/gh/spore-host/spore-host-plugin-tailscale/branch/main/graph/badge.svg)](https://codecov.io/gh/spore-host/spore-host-plugin-tailscale)
[![License](https://img.shields.io/badge/license-Apache%202.0-blue.svg)](LICENSE)

Tailscale ephemeral-node plugin for [spore-host](https://github.com/spore-host/spore-host).

```bash
spawn plugin install github:spore-host/spore-host-plugin-tailscale/tailscale \
  --instance i-0abc123 \
  --config auth_key=tskey-auth-xxxxxxxxxxxx
```
