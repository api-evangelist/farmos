# farmOS

Open-source farm management and record-keeping system with a JSON:API-based REST API for managing assets, logs, plans, and farm records. Supports self-hosted deployments and managed hosting via Farmier.

## API

farmOS exposes a JSON:API compliant REST API via the `farm_api` module. All endpoints use the `/api` path prefix and return JSON:API formatted responses with UUID-based resource identifiers.

- **Root endpoint:** `/api` — returns server metadata, farm details, version, and authenticated user info
- **Schema endpoint:** `/api/schema` — JSON Schema graph of all available API resources
- **Resource pattern:** `/api/[entity-type]/[bundle]` (e.g., `/api/log/activity`)

## Authentication

OAuth2 with three supported grant types:

- **Authorization Code** — recommended for third-party integrations
- **Password Credentials** — legacy, first-party use only
- **Client Credentials** — machine-to-machine server integrations

Token endpoint: `/oauth/token`
Bearer header: `Authorization: Bearer {access_token}`

OAuth scopes: `farm_manager`, `farm_worker`, `farm_viewer`

## SDKs

- **farmOS.js** — JavaScript/Node.js library: `npm install farmos` | [Docs](https://farmos.org/development/farmos-js/) | [GitHub](https://github.com/farmOS/farmOS.js)
- **farmOS.py** — Python library: `pip install farmOS~=1.0.0b` | [Docs](https://farmos.org/development/farmos-py/) | [GitHub](https://github.com/farmOS/farmOS.py)

## Hosting

- **Self-hosted:** Free, runs on any LAMP/LEMP stack. See [installation docs](https://farmos.org/hosting/).
- **Farmier managed hosting:** $75/year base, includes 1 GB storage. [farmier.com/pricing](https://farmier.com/pricing/)

## Links

- Website: https://farmos.org/
- API Docs: https://farmos.org/development/api/
- GitHub Org: https://github.com/farmOS
- Blog: https://farmos.org/blog/
- Forum: https://farmos.discourse.group/
- Open Collective: https://opencollective.com/farmos
- X: https://twitter.com/farmOSorg

## APIs.json

This repository contains an [APIs.json](apis.yml) index cataloging the farmOS API along with supporting files for plans, rate limits, and FinOps guidance.
