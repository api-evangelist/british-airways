# British Airways (british-airways)

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

British Airways Plc is the United Kingdom's flag carrier, headquartered at Waterside near London Heathrow and owned since 2011 by International Consolidated Airlines Group (IAG), which also owns Iberia, Aer Lingus, Vueling and LEVEL. In the distribution chain BA is a supplier of its own seat inventory, reached either through the three legacy GDSs, through IATA NDC connections it operates itself, or direct on ba.com. BA was one of the earliest and most aggressive NDC adopters: from 1 November 2017 IAG applied a per-fare-component Distribution Technology Charge to BA and Iberia marketed fares that are not booked through an NDC based connection or a low-cost channel such as ba.com, explicitly pricing GDS intermediation out of the stack. Its API posture is honest to state plainly — the NDC distribution API is real and is built on the IATA EDIST message set, but there is no public specification, no published base URL, no self-serve signup and no exit path.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/british-airways/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/british-airways/refs/heads/main/apis.yml)

## Tags

- Travel
- United Kingdom
- Aviation
- Airline
- Distribution
- NDC
- Booking
- Corporate Travel
- Airports

## Timestamps

- **Created:** 2026-07-28
- **Modified:** 2026-07-28

## APIs

### British Airways NDC API

British Airways' IATA New Distribution Capability API — a direct link into BA's host reservation system for flight shopping, ordering, ticketing and post-booking servicing, operated jointly across IAG for BA and Iberia. It implements the IATA EDIST message set (the ndc.ba.com application carries the XML namespace `http://www.iata.org/IATA/EDIST/2017.2`), with a 21.3 pilot programme running alongside the 17.2 production version. The IAG developer portal described the 17.2 plan as AirShopping, OfferPrice, SeatAvailability, OrderCreate, OrderRetrieve, AirDocIssue, OrderChange, OrderReShop and OrderChangeNotif. No OpenAPI or WSDL is published, no production base URL is published, and there is no self-serve access.

- **Human URL:** [https://ndc.ba.com/developer/api-documentation](https://ndc.ba.com/developer/api-documentation)
- **Base URL:** not published

#### Tags

- NDC
- Distribution
- Flights
- Booking
- Ticketing

#### Properties

- [Documentation](https://ndc.ba.com/developer/api-documentation)
- [Portal](https://ndc.ba.com/)
- [Getting Started](https://ndc.ba.com/start/build-and-test-the-api)
- [Signup](https://ndc.ba.com/start/ndc-registrations)
- [Support](https://ndc.ba.com/faq/technical)
- [Documentation — Offer Management](https://ndc.ba.com/capability/ndc-offer-management)
- [Documentation — Order Management](https://ndc.ba.com/capability/ndc-order-management)
- [Legacy Portal](https://developer.iairgroup.com/british_airways) — HTTP 404 as of 2026-07-28

## Common Properties

- [Website](https://www.britishairways.com/)
- [Portal](https://ndc.ba.com/)
- [Partner Portal](https://www.britishairways.com/travel-partner-connect/en/kr/policies/booking-and-ticketing/distribution-technology-charge-guide)
- [Documentation — Distribution Technology Charge Guide](https://www.britishairways.com/assets/pdfs/updates/distribution-technology-charge.pdf)
- [Legacy Portal](https://developer.iairgroup.com/british_airways)
- [Newsroom](https://mediacentre.britishairways.com/)
- [Investors](https://www.iairgroup.com/)
- [LinkedIn](https://www.linkedin.com/company/british-airways)

## Switching Cost

Recorded in full in [review.yml](review.yml).

| Dimension | Value |
| --- | --- |
| Interface shape | `standard-plus-proprietary` — IATA NDC / EDIST 17.2, extended with BA-specific per-message versions and certification |
| Second source | `no-alternative` — the connection is swappable, the inventory is not |
| Exit path | `no-export-published` — no export, dump or bulk operation in the NDC message set |
| Identifier portability | IATA airport/city codes, BA/BAW designators, PNR record locators, IATA 125 ticket prefix — but BA-minted OfferIDs, OrderIDs and client-keys for anything that matters |
| Contractual lock-in | Distribution Technology Charge applied per fare component to every non-NDC booking since 1 Nov 2017 |
| Access gate | `commercial-agreement` — Trial Use Agreement, B1/B2 certification form, Travel Agency Addendum for IATA agents, signed Live API Contracts |
| Distribution model | `ndc-direct`, with GDS available and surcharged |

## Artifacts

| Artifact | File | Method |
| --- | --- | --- |
| Authentication | [authentication/british-airways-authentication.yml](authentication/british-airways-authentication.yml) | searched |
| OAuth scopes | [scopes/british-airways-scopes.yml](scopes/british-airways-scopes.yml) | searched |
| Well-known | [well-known/british-airways-well-known.yml](well-known/british-airways-well-known.yml) | searched |
| OIDC discovery (verbatim) | [well-known/british-airways-openid-configuration.json](well-known/british-airways-openid-configuration.json) | searched |
| Conventions | [conventions/british-airways-conventions.yml](conventions/british-airways-conventions.yml) | searched |
| Lifecycle | [lifecycle/british-airways-lifecycle.yml](lifecycle/british-airways-lifecycle.yml) | searched |
| Conformance | [conformance/british-airways-conformance.yml](conformance/british-airways-conformance.yml) | searched |
| Event surface (OrderChangeNotif) | [asyncapi/british-airways-ndc-notifications.yml](asyncapi/british-airways-ndc-notifications.yml) | searched |
| Sandbox | [sandbox/british-airways-sandbox.yml](sandbox/british-airways-sandbox.yml) | searched |
| Packages | [packages/british-airways-packages.yml](packages/british-airways-packages.yml) | searched |
| Vulnerability disclosure | [security/british-airways-vulnerability-disclosure.yml](security/british-airways-vulnerability-disclosure.yml) | searched |
| Domain security | [security/british-airways-domain-security.yml](security/british-airways-domain-security.yml) | probed |
| llms.txt | [llms/british-airways-llms.txt](llms/british-airways-llms.txt) | generated |

Not produced, because nothing real exists to produce them from: `openapi/`, `overlays/`, `grpc/`, `errors/`, `data-model/`, `skills/`, `mcp/`, `cli/`, `components/`, `changelog/`.

## Notes

- There is **no self-serve developer portal**. The only live API-facing property is [ndc.ba.com](https://ndc.ba.com/), whose documentation and sandbox sit behind a Microsoft Entra External ID login.
- The IAG Developer Programs portal at `developer.iairgroup.com` — which carried BA's public consumer REST APIs (Flight Information, Flight Offers, Lowest Prices, In-Flight Entertainment, Hotel/Car/Flight packages) — returned HTTP 404 for every path on 2026-07-28. The Internet Archive shows it live as recently as 2026-02-11.
- `api.ba.com` returns `ERR_596_SERVICE_NOT_FOUND` for every documented resource. BA's public REST API is decommissioned.
- No OpenAPI, Swagger, WSDL or Postman collection is published anywhere. Nothing was harvested into `openapi/`.
- British Airways publishes no GitHub organisation and no SDKs. npm, PyPI, Maven Central, NuGet, RubyGems, Packagist, crates.io and pkg.go.dev were all searched on 2026-07-28 — zero first-party client libraries.
- The one machine-readable document British Airways does serve is an **OpenID Connect discovery document**, at the Microsoft Entra External ID (CIAM) tenant `45c0456f-2aef-40f6-847e-d3d957348527` that the NDC hub logs developers into. It is saved verbatim in `well-known/`. It governs hub login, not API authorisation.
- British Airways runs a real, public **vulnerability disclosure programme on HackerOne** ([british_airways_vdp](https://hackerone.com/british_airways_vdp)) — open submissions, no bounties, wildcard scopes `*.britishairways.com` and `*.ba.com`, which puts `ndc.ba.com` in scope. There is no `/.well-known/security.txt` on any BA host.
- No trust centre, no named certifications, no status page, no SLA, no deprecation policy and no dated changelog were found, so no `Compliance`, `StatusPage` or `Deprecation` pointer is emitted.
