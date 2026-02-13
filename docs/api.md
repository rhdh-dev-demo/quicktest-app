# API Reference

This document describes the REST API endpoints provided by quicktest-app.

## Base URL

| Environment | Base URL |
|-------------|----------|
| Development | `https://quicktest-app-quicktest-app-dev.apps.rosa.nj88g-soani-kii.ivwd.p3.openshiftapps.com` |
| Staging | `https://quicktest-app-quicktest-app-staging.apps.rosa.nj88g-soani-kii.ivwd.p3.openshiftapps.com` |
| Production | `https://quicktest-app-quicktest-app-prod.apps.rosa.nj88g-soani-kii.ivwd.p3.openshiftapps.com` |

---

## Endpoints

### Health Check

Check if the application is running and healthy.

```
GET /health
```

#### Response

```json
{
  "status": "UP",
  "service": "RHDH Demo Application",
  "timestamp": "2024-01-15T10:30:00.000Z"
}
```

| Field | Type | Description |
|-------|------|-------------|
| `status` | string | Health status (`UP` or `DOWN`) |
| `service` | string | Service name |
| `timestamp` | string | ISO 8601 timestamp |

#### Example

```bash
curl https://quicktest-app-quicktest-app-dev.apps.rosa.nj88g-soani-kii.ivwd.p3.openshiftapps.com/health
```

---

### Readiness Check

Check if the application is ready to receive traffic.

```
GET /ready
```

#### Response

```json
{
  "status": "UP",
  "ready": true
}
```

| Field | Type | Description |
|-------|------|-------------|
| `status` | string | Readiness status |
| `ready` | boolean | Whether the app is ready |

#### Example

```bash
curl https://quicktest-app-quicktest-app-dev.apps.rosa.nj88g-soani-kii.ivwd.p3.openshiftapps.com/ready
```

---

### Environment Info

Get the current deployment environment.

```
GET /env
```

#### Response

```json
{
  "environment": "dev"
}
```

| Field | Type | Description |
|-------|------|-------------|
| `environment` | string | Current environment (`dev`, `staging`, or `prod`) |

#### Example

```bash
curl https://quicktest-app-quicktest-app-dev.apps.rosa.nj88g-soani-kii.ivwd.p3.openshiftapps.com/env
```

---

## Response Codes

| Code | Description |
|------|-------------|
| `200` | Success |
| `404` | Endpoint not found |
| `500` | Internal server error |

## OpenAPI Specification

The full OpenAPI 3.0 specification is available at:

- [openapi.yaml](https://github.com/rhdh-dev-demo/quicktest-app/blob/main/api/openapi.yaml)

You can also view it in the Backstage API catalog.

## Rate Limiting

Currently, there are no rate limits applied to these endpoints.

## Authentication

These endpoints are publicly accessible and do not require authentication.

!!! note "Production Consideration"
    In a production environment, you may want to add authentication to sensitive endpoints.

