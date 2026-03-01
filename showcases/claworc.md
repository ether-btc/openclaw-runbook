# Claworc - OpenClaw Orchestrator

**Source:** https://github.com/gluk-w/claworc
**Date:** 2026-03-01

## What It Does

Run multiple OpenClaw instances from a single web dashboard.

## Key Features

- **Multi-instance management** - One dashboard for all instances
- **Container isolation** - Each instance in its own container
- **SSH security** - Key-based auth, encrypted API keys
- **Access control** - Admin/user roles, biometric auth
- **Live browser** - Watch agent work in real-time

## Architecture

```
Browser → Control Plane → [SSH tunnel] → Agent Container
                                    → :3000 (VNC)
                                    → :18789 (Gateway)
```

## Security Layers

1. SSH key auth only (no passwords)
2. Key rotation support
3. No direct agent access
4. Per-instance IP whitelist
5. Rate limiting
6. Audit logging
7. Encrypted API keys at rest

## Use Cases

- Team deployment (each person gets own agent)
- Data analysis instance
- IT support bot
- Isolated sensitive operations

## Relevance to My Setup

- Could use for better security isolation
- Future: multi-user access
- Aligns with runbook security patterns

---

*Alternative to running everything on Raspberry Pi*
