# Backend Release Checklist

Use before releasing or deploying a backend service.

## Code And Tests

- [ ] Unit tests pass.
- [ ] Integration tests pass, if available.
- [ ] API contract changes are documented.
- [ ] Backward compatibility is reviewed.
- [ ] Error handling is reviewed.

## Configuration

- [ ] Environment variables are documented.
- [ ] Secrets are not committed.
- [ ] Feature flags are in the expected state.
- [ ] Logging is appropriate.
- [ ] Monitoring is ready.

## Data And Migration

- [ ] Migration plan is documented.
- [ ] Migration dry-run completed, if possible.
- [ ] Rollback plan is documented.
- [ ] Data retention implications are reviewed.
- [ ] Production database writes require human confirmation.

## Deployment Gate

- [ ] Deployment target is confirmed.
- [ ] Payload or operation details are documented.
- [ ] Impact scope is documented.
- [ ] Rollback plan is documented.
- [ ] Recovery path is documented.
- [ ] Revert method is documented.
- [ ] Known rollback limitations are documented.
- [ ] Human has explicitly approved deployment.

Deployment requires human confirmation:

- target
- payload or operation details
- impact scope
- rollback plan, recovery path, revert method, and known limitations
