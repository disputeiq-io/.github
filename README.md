# disputeiq-platform/.github (`diq-org-github`)

Organization profile and reusable GitHub Actions workflows for DisputeIQ.

## Reusable Workflows

- [java-service.yml](.github/workflows/java-service.yml): Commitlint, Maven `verify` (Spotless, Checkstyle, JUnit/Testcontainers, JaCoCo), Trivy scan, optional eval gate, Jib + cosign + OCI Helm push.
- [web-app.yml](.github/workflows/web-app.yml): Commitlint, `npm ci`, ESLint (`--max-warnings=0`), Prettier check, `tsc`, Vitest, and Vite build.
- [helm-chart.yml](.github/workflows/helm-chart.yml): Strict `helm lint` and `kubeconform` schema validation.
