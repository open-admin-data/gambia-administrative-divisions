# Gambia Administrative Divisions / Gambia



## Overview

| Item | Details |
|------|---------|
| Local Government Area | 8 |
| District | 49 |
| Ward | 115 |
| Coordinates | ✅ Included (all levels) |
| Formats | JSON, NDJSON, CSV |
| License | CC-BY-4.0 |
| Last Updated | 2026-05-27 |
| Website | [openadmindata.org/gm](https://openadmindata.org/gm/) |
| API | [openadmindata.org/api/gm](https://openadmindata.org/api/gm/) |

## Browse by Local Government Area

| # | Local Government Area | Districts | Wards | Link |
|---|----|----|----|------|
| 1 | Banjul City Council | 3 | 9 | [Browse](divisions/banjul-city-council-gm01/) |
| 2 | Central River North | 5 | 10 | [Browse](divisions/central-river-north-gm07/) |
| 3 | Central River South | 6 | 12 | [Browse](divisions/central-river-south-gm04/) |
| 4 | Kanifing Municipal Council | 6 | 18 | [Browse](divisions/kanifing-municipal-council-gm05/) |
| 5 | Lower River | 6 | 12 | [Browse](divisions/lower-river-gm08/) |
| 6 | North Bank | 7 | 16 | [Browse](divisions/north-bank-gm06/) |
| 7 | Upper River | 7 | 14 | [Browse](divisions/upper-river-gm02/) |
| 8 | West Coast | 9 | 24 | [Browse](divisions/west-coast-gm03/) |

## Data Files

| File | Format | Description |
|------|--------|-------------|
| [all-lga.json](data/all-lga.json) | JSON | All 8 local government area records |
| [all-district.json](data/all-district.json) | JSON | All 49 district records |
| [all-ward.json](data/all-ward.json) | JSON | All 115 ward records |
| [all-flat.json](data/all-flat.json) | JSON | Levels 1-2 flat array |
| [all-flat.ndjson](data/all-flat.ndjson) | NDJSON | Streaming format |
| [all-flat.csv](data/all-flat.csv) | CSV | Spreadsheet format |
| [hierarchy.json](data/hierarchy.json) | JSON | Nested tree |
| [schema.json](data/schema.json) | JSON Schema | Data schema |

## Quick Start

### Python

```python
import json

with open("data/all-lga.json", "r", encoding="utf-8") as f:
    data = json.load(f)

for r in data:
    print(f"{r['name']['local']} ({r['name']['en']}) — {r['children_count']['district']} districts")
```

### JavaScript

```javascript
import { readFileSync } from "fs";

const data = JSON.parse(readFileSync("data/all-lga.json", "utf-8"));
console.log(`Total: ${data.length} local government areas`);
```

## Schema

| Field | Type | Description |
|-------|------|-------------|
| `id` | string | Unique identifier |
| `level` | integer | 1=local government area, 2=district, 3=ward |
| `level_name` | object | Level label (local + English) |
| `name.local` | string | Name in local script |
| `name.en` | string | English name |
| `name.slug` | string | URL-safe slug |
| `parent` | object/null | Parent division reference |
| `ancestors` | array | Full ancestor chain |
| `children_count` | object | Count of children per level |
| `zip_codes` | array | Postal codes (where available) |
| `geo.lat` | string | Latitude (WGS84) |
| `geo.lon` | string | Longitude (WGS84) |

Full schema: [data/schema.json](data/schema.json)

## Hierarchy Browse

```
divisions/{lga-slug}/
divisions/{lga-slug}/{district-slug}/
```

Wards are listed inline in each district's README.

## AI Integration

- [llms.txt](docs/llms.txt) — Quick reference for AI agents
- [llms-full.txt](docs/llms-full.txt) — Summary with per-local government area links
- [Per-local government area data](docs/llms-full/) — Full data by local government area

## Citation

```
Gambia Administrative Divisions Dataset (CC-BY-4.0)
URL: https://github.com/open-admin-data/gambia-administrative-divisions
```

See [CITATION.cff](CITATION.cff) for machine-readable citation.

## License

- **Data**: [CC-BY-4.0](LICENSE)

## Related

- [Open Admin Data](https://openadmindata.org) — Browse, search and explore administrative divisions for every country
- [open-admin-data](https://github.com/open-admin-data) — GitHub organization with all country repos
- [ListBase](https://www.listbase.org) — Structured reference data for every country
