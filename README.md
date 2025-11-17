

location-map.json is a structured geospatial dataset used by GARI (Global Alert Relay Interface) and CORA (Correlating Operations & Reasoning Architecture).
It defines global static zones, including:

Capitals

Major cities

Ports

Airports

Shipping lanes

Chokepoints

Rail corridors

Pipeline corridors

Power grid corridors

Weather basins

Energy zones

Mining zones

Agriculture zones

Fishery zones

Refining & storage zones

Maritime territorial claims

Fiber landing stations

Data centers

Space launch sites

Satellite ground stations

Water scarcity zones

Drought zones

Reservoir zones

Timber/forestry zones

Rare earth processing zones

And other predefined global areas of interest

These static zones act as the foundation layer for spatial correlation in GARI/CORA.
Dynamic events (futures, crypto, news, AIS, weather, etc.) can be mapped against these static regions to determine proximity, impact, and correlation strength.

Purpose

This dataset provides:

Geospatial Anchors

Each entry defines a coordinate center and sometimes an AOI region or bounding box.

Categorization & Structure

Zones are organized by thematic category for fast lookup and classification.

AI / Event Correlation Support

CORA uses these static anchors as part of its long-term memory reference system when:

linking new events to known global regions

visualizing activity clusters on the 3D GARI globe

running proximity-based correlation logic

tagging events with region, risk zone, or infrastructure type

Format

The file uses a flat JSON object with no nested indentation for blocks (per design preference), for example:

"strait_of_hormuz": {
  "center": [26.566, 56.250],
  "radius_km": 150
},
"panama_canal": {
  "center": [9.101, -79.704],
  "radius_km": 120
}


Each static zone includes:

center: [lat, lon]

optional: radius, polygon, or AOI metadata

label: human-readable name

category: (optional) classification for downstream apps

This structure makes the file flexible, easy to parse, and compatible with both GARI (visual globe renderer) and CORA (memory/correlation engine).

Usage

You can import this file in any backend or frontend system:

import locations from './location-map.json';

// Example
console.log(locations["strait_of_hormuz"].center);


Or load it into a database to support geospatial indexing.

License / Notice

This file contains non-sensitive, manually assembled, high-level geospatial reference data.
It does not include any proprietary algorithms, correlation logic, decay weights, or memory architecture from CORA.
It is safe for open-source publication.

Contributing

If you want to add more zones:

Use the existing flat structure format

Follow naming conventions (snake_case keys)

Include coordinates and radius/polygon if applicable

Submit a pull request.

Contact
ian.carroll@thisisgari.com
For questions or collaboration on GARI / CORA / PARKSystems:

PARKSystems Corporation
Where Exception Is Normal
(c) 2025
