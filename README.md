# Rooftop Solar Suitability API

**True rooftop detection from lat/lng — no manual area input required.**  
OpenStreetMap building detection · NREL usable area fractions · PVWatts V8 yield · IFC setback compliance.

[![RapidAPI](https://img.shields.io/badge/RapidAPI-Subscribe-0055DA?style=flat-square)](https://rapidapi.com/bethelnedi/api/rooftop-solar-suitability-api)
[![Docs](https://img.shields.io/badge/API_Docs-Swagger-85EA2D?style=flat-square)](https://amfumu-rooftop-solar-suitability-api.hf.space/docs)

## How It Works

```
lat/lng → OpenStreetMap Overpass API → building polygon
→ Shoelace formula (Bourke 1988) → footprint area (m²)
→ NREL usable fraction (Gagnon et al. 2016) → usable roof area
→ IFC 2021 §1504.3 setback deduction → net usable area
→ PVWatts V8 yield model → annual kWh
→ NREL ATB 2024 CAPEX → financials + ITC
→ Suitability score 0–100
```

## Quick Start

```bash
curl -X POST https://rooftop-solar-suitability-api.p.rapidapi.com/rooftop/quick \
  -H "X-RapidAPI-Key: YOUR_KEY" \
  -H "Content-Type: application/json" \
  -d '{
    "latitude": 33.4484,
    "longitude": -112.0740,
    "state": "AZ",
    "building_type": "warehouse"
  }'
```

## Citation Register
- Gagnon et al. (2016) NREL/TP-6A20-65298 — rooftop usable fractions by building type
- NREL PVWatts V8 — NREL/TP-6A20-62641
- IFC 2021 §1504.3 — fire access setback requirement
- Cole & Karmakar (2023) NREL/TP-6A40-85332 — CAPEX benchmarks
- IRA 2022 §48E — 30% base ITC
- Bourke (1988) — polygon area via Shoelace formula
- OpenStreetMap ODbL 1.0

## Topics
`rooftop-detection` `solar-potential` `openstreetmap` `pvwatts` `solar-roi` `building-footprint` `gis` `nrel` `shoelace-formula` `solar-suitability` `rooftop-solar` `lat-lng` `building-detection` `fastapi` `python` `rapidapi`

