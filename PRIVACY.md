# Privacy Policy – Katastero

**Last updated: 2026-11-05**

Katastero is a browser extension that displays official Spanish
geographic data on real-estate portal maps and analyses parcels against
public government geoservices.

## Data collection

**The extension collects no personal data.** Nothing you view, click or
analyse is sent to the developer or to any third-party analytics service.
There is no telemetry, no tracking, no advertising, no account system.

The only third-party request is licence verification: when you activate
a purchased licence key, the key and a random, per-install device id are
sent directly to `api.polar.sh` (our store vendor / merchant of
record) to register this device, and re-checked there about every three
days. No browsing data, coordinates or listing data are included in
these requests. Purchases themselves happen on Polar's checkout;
their own privacy policy applies there.

## What the extension does with data

- **Map coordinates:** When you click a map point or open a listing page,
  the clicked/listing coordinates are sent – directly from your browser –
  to the official public geoservices of the Spanish national
  administrations (Dirección General del Catastro, Ministerio de
  Vivienda, MITECO/IEPNB, IGN, IGME, INE, SIGPAC), the regional and
  foral authorities (Gobierno de Canarias GRAFCAN, Diputaciones of
  Navarra/Álava/Bizkaia/Gipuzkoa, Generalitat Valenciana) and the EU
  JRC PVGIS service to retrieve public map data. These services
  answer public WMS/WFS/ArcGIS requests; they receive only the queried
  coordinates, like any normal map pan in a GIS viewer.
- **Listings:** On supported portals, listing coordinates already present
  in the page's own API responses are read locally in your browser to run
  the same public geodata queries. They are not uploaded anywhere else.
- **Settings:** Your preferences (enabled layers, opacity, panel
  visibility) are stored via `chrome.storage.sync` – they sync through
  your own Google account using Chrome's built-in mechanism. The
  developer has no access to them.
- **Licence:** Your licence key is stored in `chrome.storage.sync` (so
  it works on your own Chrome devices); this device's instance id and
  last validation time are stored in `chrome.storage.local`. The
  developer never receives either.
- **Cache:** Analysis results are cached in-memory per browser session
  only and discarded on restart.

## Permissions justification

| Permission | Reason |
|---|---|
| `storage` | Save user preferences (layers, opacity, panel) and licence state. |
| `alarms` | Periodic background licence revalidation (every 12 h while the browser runs). |
| `host_permissions` (gov domains) | Required to fetch public map images and feature data from the official Spanish geoservices listed above. |
| `host_permissions` (api.polar.sh) | Required to activate and periodically revalidate the licence key. |
| `content_scripts` (portal + Google Maps domains) | Required to draw the overlays and controls on the supported real-estate portals and on embedded/hosted Google Maps views they use. |

## Legal basis & data transfers (GDPR)

- Licence verification is necessary to perform the purchase contract
  (Art. 6(1)(b) GDPR). Only the licence key and the random device id are
  transmitted — no name, e-mail, browsing or location data.
- Licence requests go to Polar (Polar Software Inc., merchant of
  record). Processing there is governed by their privacy policy; the
  developer receives no copy of these requests.
- Everything else runs locally in your browser. Settings and licence key
  sync only through your own Google account via Chrome's storage sync.

## Data sharing

No data is sold, shared or transferred to any third party, ever — apart
from the licence-verification calls described above, which carry no
personal data beyond the key you were given and a random id.

## Chrome Web Store Limited Use

The use of information received from Google APIs adheres to the Chrome
Web Store User Data Policy, including the Limited Use requirements.
The extension reads the on-page map/listing data of supported sites only
to query the public geoservices described above; it does not collect,
sell or transmit browsing activity, and nothing is used for advertising,
credit-worthiness or any unrelated purpose.

## Contact

For questions, open an issue on the project page linked in the Chrome
Web Store listing.
