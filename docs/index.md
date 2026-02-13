# quicktest-app

A Node.js application

## Overview

This application was created using a **Red Hat Developer Hub software template**. Everything you need to build, test, and deploy is already configured:

- ✅ Source code repository
- ✅ GitOps configuration repository
- ✅ CI/CD pipelines (Tekton)
- ✅ Deployment manifests (Helm)
- ✅ ArgoCD applications for all environments

## Quick Start

### Local Development

```bash
# Clone the repository
git clone https://github.com/rhdh-dev-demo/quicktest-app.git
cd quicktest-app

# Install dependencies
yarn install

# Start the development server
yarn start
```

The application will be available at `http://localhost:3000`.

### Endpoints

| Endpoint | Description |
|----------|-------------|
| `GET /` | Main application page |
| `GET /health` | Health check (liveness probe) |
| `GET /ready` | Readiness check |
| `GET /env` | Current environment info |

## Environments

| Environment | Namespace | URL |
|-------------|-----------|-----|
| Development | `quicktest-app-dev` | [View in ArgoCD](https://openshift-gitops-server-openshift-gitops.apps.rosa.nj88g-soani-kii.ivwd.p3.openshiftapps.com/applications/quicktest-app-dev) |
| Staging | `quicktest-app-staging` | [View in ArgoCD](https://openshift-gitops-server-openshift-gitops.apps.rosa.nj88g-soani-kii.ivwd.p3.openshiftapps.com/applications/quicktest-app-staging) |
| Production | `quicktest-app-prod` | [View in ArgoCD](https://openshift-gitops-server-openshift-gitops.apps.rosa.nj88g-soani-kii.ivwd.p3.openshiftapps.com/applications/quicktest-app-prod) |

## Repositories

| Repository | Purpose |
|------------|---------|
| [Source Code](https://github.com/rhdh-dev-demo/quicktest-app) | Application source code |
| [GitOps](https://github.com/rhdh-dev-demo/quicktest-app-gitops) | Kubernetes manifests and ArgoCD configs |

## Making Changes

1. **Edit code** in the source repository
2. **Push to main** branch
3. **Tekton pipeline** automatically builds and deploys to DEV
4. **Promote to staging** using the promote pipeline
5. **Promote to production** after validation

!!! tip "GitOps Workflow"
    All deployments are managed through Git. Changes to the GitOps repository automatically sync to the cluster via ArgoCD.

## Support

- **Owner**: group:default/ui-team
- **Documentation**: You're reading it!
- **API Reference**: See the [API docs](api.md)

