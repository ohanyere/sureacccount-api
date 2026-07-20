# Runbook

## Service

- Name: `sureacccount-api`
- Team: `Platform Engineering`
- Owner: `mooref068@gmail.com`
- Cost center: `platform-engineering`

## First Checks

```bash
kubectl get rollout sureacccount-api -n sureacccount-api-dev
kubectl get pods -l app.kubernetes.io/name=sureacccount-api -n sureacccount-api-dev
kubectl logs -l app.kubernetes.io/name=sureacccount-api -n sureacccount-api-dev
```

## Health

```bash
curl https://sureacccount-api.dev.platform.ohanyere.internal/healthz
curl https://sureacccount-api.dev.platform.ohanyere.internal/readyz
curl https://sureacccount-api.dev.platform.ohanyere.internal/livez
```

## Rollback

```bash
kubectl argo rollouts undo sureacccount-api -n sureacccount-api-dev
```

Escalate to `Platform Engineering` through `mooref068@gmail.com` if rollback does not restore service.
