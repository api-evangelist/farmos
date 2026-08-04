# farmOS

<!-- API-EVANGELIST-PROVENANCE:BEGIN -->
> ### About this repository
>
> **This is not our API.** This repository is an independent, third-party profile of a company's
> **publicly available** API surface, maintained by [API Evangelist](https://apievangelist.com).
> API Evangelist does not operate, host, resell, or support this company's APIs, and is not
> affiliated with or endorsed by the company unless stated on the profile.
>
> **Where the information came from.** Everything here is assembled from material a member of the
> public can reach with a browser and no credentials — the company's own website, developer portal
> and documentation, the specifications it publishes for public use (OpenAPI, AsyncAPI, JSON Schema,
> `apis.json`, `llms.txt` and similar), its public repositories, and its public status, pricing and
> changelog pages. **Nothing here is obtained by breaching a system, defeating an access control, or
> using credentials of any kind.**
>
> **The rating is an independent assessment.** The Kin Score and Agent Readiness rating are
> independently calculated scores of a company's *public* API artifacts, produced by API Evangelist
> against a published rubric. They are not certifications, endorsements, security assessments, or
> audits, and they score published artifacts — not the quality, safety, or security of the software.
>
> **Corrections, re-scores, and removal are free.** No partnership, contract, or purchase is
> required, and you do not need to justify the request.
>
> - **Something wrong?** Open an issue on this repository, or email
>   [info@apievangelist.com](mailto:info@apievangelist.com).
> - **Published something new?** Ask for a re-score and we will re-run the rating.
> - **Want the listing taken down?** Say so and we will honor it. The profile is reduced to your
>   company name, a factual description, and a link to your own site, and the company is recorded as
>   **unrated** — never scored zero for having asked.
>
> **Response times.** Acknowledgement within **one business day**; removal or restriction within
> **two business days**; corrections and re-scores within **five business days**.
>
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

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
