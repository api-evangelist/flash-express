# Flash Express

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

Flash Express is a Bangkok-headquartered express parcel delivery and e-commerce logistics operator
serving Thailand, with affiliated operations in the Philippines and Laos. It publishes the
**FlashExpress Open API**, a merchant-facing integration surface for creating shipments, printing
waybill labels, tracking parcels, estimating freight rates, scheduling courier pickups and
subscribing to delivery webhooks.

- Website: https://flashexpress.com/en/
- Developer documentation: https://open-docs.flashexpress.com/
- Production API base URL: https://open-api.flashexpress.com
- Training API base URL: https://open-api-tra.flashexpress.com

### Notes on this profile

The FlashExpress Open API is fully and publicly documented, but it is a signed form-post API rather
than a REST API, and it ships **no machine-readable contract** — no OpenAPI, AsyncAPI, GraphQL or
MCP surface exists (all hosts were probed). Artifacts in this repository were therefore read from the
provider's published HTML reference and recorded with their real provenance, rather than derived from
a spec. Notable characteristics captured here: every operation is `POST` including reads, business
errors are returned with HTTP 200 and a code in the body, authentication is SHA256 shared-secret
request signing, weight is always grams and money always integer cents, and there is no idempotency
key. A real webhook surface (five event types, signed callbacks, automatic redelivery) is documented
and captured in `asyncapi/`.
