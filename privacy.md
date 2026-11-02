# PocketMap Privacy Policy

_Last updated: 2026-11-02 (0.6.1). Applies to the PocketMap iOS app (co.superduperai.pocketmap), version 0.3 and later, and to this website._

**In short:** PocketMap has no account and no advertising. From version 0.6.1 the app sends
anonymous usage counts (which features are used, never where), and you can switch them off in
Settings. Up to 0.6.0 the app sent us nothing at all. The other thing we host ourselves is a
folder of static routing-graph and survival-POI files (see below); it keeps no logs we read.

**App Privacy label from 0.6.1:** Usage Data (Product Interaction) and Identifiers (Device ID),
both *not linked to you*, *not used for tracking*, purpose *Analytics*. The "Device ID" is the
random install ID described below, not Apple's advertising or vendor identifier.

## Location

Your location is used on the phone only: to show where you are on the map, to follow you, to
record a track while the app is open, to point the way back to a spot you saved, and as the start
of a route you ask for. It is never sent anywhere by us. The only time a position leaves the phone
is when you tap Walk, Bike or Drive and the route cannot be computed on the phone (see Valhalla
below). You can deny the permission and everything else keeps working.

## Network requests the app makes

Every request the app can make is listed here. Each one carries your IP address, as any web request
does. None carries an identifier for you or your device beyond that.

- **OpenFreeMap** (`tiles.openfreemap.org`): map style, fonts and tiles, when you view the map
  online or download a region for offline use. Requests contain the tile coordinates, which reveal
  the area you are looking at. See [openfreemap.org](https://openfreemap.org).
- **PocketMap graph and survival-POI tiles** (`pub-1a1f840e4f3a40528a52b437de2fb49c.r2.dev`,
  static files in a Cloudflare R2 bucket published by us; `pocketmap-graph.pages.dev`, the older
  Cloudflare Pages host, is asked only when the first does not answer): the routing graph for an
  area and, from 0.4, the water / shelter / medical points of interest for the same area (the
  `poi/` prefix of the same bucket), downloaded together with a region so that routes and the
  Nearby screen work on the phone with no network. Requests contain the tile coordinates of the
  area you download, nothing else. Cloudflare's own handling of requests is described in
  [Cloudflare's privacy policy](https://www.cloudflare.com/privacypolicy/).
- **Terrain tiles on AWS Open Data** (`s3.amazonaws.com`, bucket `elevation-tiles-prod`, the
  Tilezen/Mapzen terrain tiles, from 0.4): elevation tiles for an area, downloaded together with a
  region, for contour lines and walking times that account for climbs. Requests contain the tile
  coordinates of the area you download, nothing else. Amazon's handling of requests to a public
  bucket is described in the [AWS privacy notice](https://aws.amazon.com/privacy/).
- **Nominatim** (`nominatim.openstreetmap.org`): only when you submit a search. The request
  contains the text you searched for. See the
  [OSMF privacy policy](https://osmfoundation.org/wiki/Privacy_Policy).
- **Valhalla on the FOSSGIS demo server** (`valhalla1.openstreetmap.de`): only when you tap Walk,
  Bike or Drive **and** the downloaded graph does not cover both ends of the route. The request
  contains the start (your current position) and the destination you chose. Routes inside a
  downloaded region never leave the phone. See [FOSSGIS e.V.](https://www.fossgis.de/datenschutzerklaerung/).
- **Open-Meteo** (`api.open-meteo.com`, `air-quality-api.open-meteo.com`): only when you switch on
  the optional wind and air-quality overlay. The request contains a grid of coordinates over the
  visible map, not your position. See [open-meteo.com](https://open-meteo.com/en/terms).

- **Our usage counter** (`analytics.superduperai.co`, from 0.6.1, unless switched off in Settings):
  the anonymous counts described under "Data we collect", sent in small batches, typically when
  the app goes to the background. No location, names, searches or tracks.

Routes computed on the phone, contour lines, the compass, nearby, daylight, sky-north and
position screens, track recording and GPX import make no requests at all.

## What lives on the phone

Downloaded map regions, their routing-graph, elevation and POI tiles, imported and recorded GPX
tracks, saved spots, the last weather answer and your settings are stored in the app's own
storage. Deleting a region in the app removes its map, graph, elevation and POI tiles; deleting
the app removes everything.

## Data we collect

**Anonymous usage counts (app 0.6.1 and later).** The app counts a few things so we know which
features matter: that the app was opened, that a region finished downloading (with its size in a
coarse bucket such as "5-20MB"), that a route was computed (walk, bike or drive, and whether it
came from the phone's graph, the online router or a straight line), and that the airport screen,
the field screens (which one), the contours-and-survival layer or a GPX import was used. Each
count carries the app version and a random ID created when the app is first opened and kept in
the app's own storage, so deleting the app deletes it. It is not Apple's advertising ID or vendor
ID, and it is not shared with any other app.

The counts **never** include your location or coordinates, place or region names, what you
searched for, your tracks or saved spots. Nothing is sent while the app's offline mode is on.
They go to our own server (`analytics.superduperai.co`, a Cloudflare Worker we run); the server
sees your IP address as part of the request, uses it with the date to make a daily hash and does
not store the IP itself. Country is taken from the request at the network edge. Counts are kept
in Cloudflare Analytics Engine for up to 3 months and may be archived in aggregate. They are not
sold, not shared and not used for advertising.

**Turn it off:** map → the map menu button → Settings and privacy → *Share anonymous usage
counts*. From then on nothing is counted and anything not yet sent is discarded.

There is no crash SDK. TestFlight crash reports and feedback, if you choose to send them, reach us
through Apple only.

## This website

This site (fortunto2.github.io/pocketmap-site) uses the same self-hosted, cookieless counter: a
page view, the page address without query string, the referring site's host name, the country
from the network edge, and the browser type. No cookies, no local storage and no fingerprint are
set; the same daily IP-and-browser hash is computed at the server and the IP is not stored. The
site is hosted by GitHub Pages, whose own handling of requests is described in the
[GitHub Privacy Statement](https://docs.github.com/site-policy/privacy-policies/github-general-privacy-statement).

## Contact

info@superduperai.co
