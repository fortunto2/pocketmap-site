# PocketMap Privacy Policy

_Last updated: 2026-11-02. Applies to the PocketMap iOS app (co.superduperai.pocketmap), version 0.3 and later._

**App Privacy label: Data Not Collected.** PocketMap has no account, no analytics and no
advertising. We, the developer, receive nothing from the app. The one thing we host ourselves
is a folder of static routing-graph files (see below); it keeps no logs we read.

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
- **PocketMap graph tiles** (`pocketmap-graph.pages.dev`, static files on Cloudflare Pages,
  published by us): the routing graph for an area, downloaded together with a region so that
  routes can be computed on the phone with no network. Requests contain the tile coordinates of the
  area you download, nothing else. Cloudflare's own handling of requests is described in
  [Cloudflare's privacy policy](https://www.cloudflare.com/privacypolicy/).
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

Routes computed on the phone, the compass, daylight, sky-north and position screens, track
recording and GPX import make no requests at all.

## What lives on the phone

Downloaded map regions, their routing-graph tiles, imported and recorded GPX tracks, saved spots,
the last weather answer and your settings are stored in the app's own storage. Deleting a region
in the app removes its map and graph tiles; deleting the app removes everything.

## Data we collect

None. There is no crash SDK and no analytics. TestFlight crash reports and feedback, if you
choose to send them, reach us through Apple only.

## Contact

info@superduperai.co
