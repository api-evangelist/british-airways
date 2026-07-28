# British Airways (british-airways)

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

## Notes

- There is **no self-serve developer portal**. The only live API-facing property is [ndc.ba.com](https://ndc.ba.com/), whose documentation and sandbox sit behind a Microsoft Entra External ID login.
- The IAG Developer Programs portal at `developer.iairgroup.com` — which carried BA's public consumer REST APIs (Flight Information, Flight Offers, Lowest Prices, In-Flight Entertainment, Hotel/Car/Flight packages) — returned HTTP 404 for every path on 2026-07-28. The Internet Archive shows it live as recently as 2026-02-11.
- `api.ba.com` returns `ERR_596_SERVICE_NOT_FOUND` for every documented resource. BA's public REST API is decommissioned.
- No OpenAPI, Swagger, WSDL or Postman collection is published anywhere. Nothing was harvested into `openapi/`.
- British Airways publishes no GitHub organisation and no SDKs.
