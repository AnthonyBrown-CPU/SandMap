# SandMap

A Qt Quick Maps desktop application for visualising a personal sand vial collection.

---

## Background

As a hobby, I travel around the North Island of New Zealand collecting sand into small glass vials with cork lids. Beaches, bays, inlets — wherever there's interesting sand. When collecting each vial, I note the latitude and longitude, the time, and the name of the location.

After accumulating a good number of vials, I wanted to visualise the collection on a map. Google Earth was the obvious candidate, but it had two problems: there was no way to embed the vial data directly into pins, and the pins had a habit of disappearing on me.

So I built my own.

---

## What It Does

- Displays an interactive map centred on the North Island of New Zealand
- Shows a marker for each collected vial at its recorded coordinates
- Clicking a marker opens an info box with the vial's name, location, and collection time
- New vials can be added by clicking any point on the map and filling in the details
- Vial data is persisted to a local database and loaded on startup

---

## Stack

- **Qt Quick / QML** — UI and map layer ([Qt Location](https://doc.qt.io/qt-5/qtlocation-index.html) with OpenStreetMap)
- **C++** — backend data model, database access
- **SQLite** (via Qt SQL) — local storage for vial records

The map plugin defaults to OpenStreetMap. Mapbox support is included but commented out — a Mapbox access token would be required to enable it.

---

## Building

Requires Qt 5.12+ with the QtLocation and QtPositioning modules.

```bash
qmake SandMap.pro
make
```

Or open `SandMap.pro` in Qt Creator and build from there.

---

## License

MIT
