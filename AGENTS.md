# AI Project Context

## Purpose
This repository is Mike Simone's fork of the frozen upstream `andreimarcu/linx-server`, used as the self-hosted media/file link service for the Signal/SMS automation stack.

## Local role / deployment
- Production instance runs on WOPR and is used by `mikesimone/signal-forwarder` to turn media attachments into expiring public links for SMS recipients.
- Uploads are protected by an authfile/API key; public reads are intentionally unauthenticated.
- Production uses a finite maximum expiry (currently documented by signal-forwarder as 14 days) and stores data on WOPR.
- The fork includes at least one local behavior beyond frozen upstream: a friendly expired/missing-file message (`expiredmessage`) rather than a bare 404. Preserve local deltas when rebasing or comparing with other active forks.

## Working rules
- Treat upstream README as historical/general documentation, not proof of Mike's production deployment.
- Check `mikesimone/signal-forwarder` and `mikesimone/Environment` for current production integration details before deployment changes.
- Avoid broad upstream modernization unless explicitly requested; this fork exists to support a specific deployed service.
- Never commit production auth keys or host secrets.
- Keep local patches small and clearly separable from upstream behavior.
