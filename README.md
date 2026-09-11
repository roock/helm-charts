# helm-charts

Kubernetes Helm Charts maintained for personal deployments.

## Available charts

- `spliit`: Deploys the [Spliit](https://github.com/spliit-app/spliit) application image.

## Usage

Add this repository as a Helm chart source:

```bash
helm repo add roock https://roock.github.io/helm-charts
helm repo update
```

Install the Spliit chart:

```bash
helm install spliit roock/spliit \
  --set postgres.host=postgresql.default.svc.cluster.local \
  --set postgres.user=spliit
```

At minimum, set `postgres.host` and `postgres.password` values before installation.

## CI/CD

- Pull requests and pushes to `main` run chart linting, template validation, and install tests.
- Pushes to `main` publish chart packages and the repository index to GitHub Pages.
