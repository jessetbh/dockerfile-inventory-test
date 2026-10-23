# Expected scan and label PR results

23 files should appear in the inventory; `services/storefront/docker/dockerfile` should not
(lowercase names aren't detected).

| Path | Inventory state | Label PR |
|---|---|---|
| `Dockerfile` | Unlabeled | Labels added after `FROM` |
| `services/checkout-api/Dockerfile` | Unlabeled | Labels added to the distroless final stage only |
| `services/catalog/Dockerfile` | Unlabeled | Labels added after the existing `maintainer` LABEL |
| `services/storefront/Dockerfile` | Unlabeled | Labels added to the `runtime` stage |
| `services/payments/Dockerfile` | Unlabeled | Labels added after the existing OCI LABEL block |
| `services/notifications/Dockerfile` | Unlabeled | Labels added after `FROM` |
| `services/search/Dockerfile` | Unlabeled | Labels added to the `runtime` stage |
| `services/recommendations/Dockerfile` | Unlabeled | Labels added after `FROM` |
| `services/recommendations/Dockerfile.gpu` | Unlabeled | Labels added after `FROM` (base image from an ARG) |
| `services/auth/Dockerfile` | Unlabeled | Labels added to the `final` stage |
| `services/inventory/Dockerfile` | Unlabeled | Labels added after `FROM` |
| `services/edge-proxy/Dockerfile` | Unlabeled | Labels added after a digest-pinned `FROM` |
| `services/legacy-billing/Dockerfile` | Unlabeled | CRLF line endings kept |
| `web/admin/Dockerfile` | Unlabeled | Labels added to the nginx stage |
| `jobs/nightly-reports/Dockerfile` | Partially labeled (stale source) | Legacy `LABEL k v` value updated in place; `source_path` added |
| `jobs/db-migrations/Dockerfile` | Labeled | No Create button / `no_changes` |
| `jobs/data-export/Dockerfile` | Partially labeled | Only `source_path` added |
| `infra/nginx-gateway/Dockerfile` | Unlabeled or partial (`$SOURCE_URL` stored literally) | Variable label left alone |
| `infra/base-images/python.Dockerfile` | Unlabeled | Labels added after `FROM` |
| `infra/base-images/Containerfile` | Unlabeled | Labels added after `FROM` |
| `tools/ci-runner/Dockerfile` | Unlabeled, empty final base image | Labels added after `FROM` |
| `tools/dev-shell/Dockerfile` | Unlabeled | Works with `# syntax=docker/dockerfile:1.7`, heredocs and cache mounts |
| `tools/nix-builder/Dockerfile` | Unlabeled | 422: non-standard `# syntax=` frontend |
