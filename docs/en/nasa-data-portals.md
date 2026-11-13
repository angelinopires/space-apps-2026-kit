# NASA data portals (general)

Each challenge page lists the datasets NASA recommends for it (see `challenges/`). This page covers the portals that work for almost any challenge, plus the traps that eat a hackathon morning.

## Start here

| Portal | What it is | Login? |
| --- | --- | --- |
| [NASA Earthdata Search](https://search.earthdata.nasa.gov/) | Search and download every NASA Earth-science dataset (satellite imagery, climate, fire, land, ocean, atmosphere) | Free Earthdata Login needed to download |
| [Worldview](https://worldview.earthdata.nasa.gov/) | Browse 1,000+ satellite layers on a map, by date. Fastest way to *see* data before downloading. Exports PNG/GeoTIFF/KMZ | No |
| [GIBS](https://www.earthdata.nasa.gov/engage/open-data-services-software/earthdata-developer-portal/gibs-api) | Tile API behind Worldview. Drop satellite imagery into Leaflet/OpenLayers/Cesium with one URL template | No |
| [data.nasa.gov](https://data.nasa.gov/) | Open data catalog across all NASA (not only Earth) | No |
| [api.nasa.gov](https://api.nasa.gov/) | Public APIs: APOD, Mars rover photos, NEO asteroids, EPIC Earth images, DONKI space weather. Free key in 1 minute | API key (free, instant) |
| [NASA Open Source Software](https://code.nasa.gov/) | NASA code you can reuse | No |
| [NASA Image and Video Library](https://images.nasa.gov/) | Public-domain images, video, audio with a JSON API | No |

## By theme

**Earth observation and climate**
- [Giovanni](https://giovanni.gsfc.nasa.gov/giovanni/): plot and analyze time series and maps of Earth-science variables in the browser, no download.
- [AppEEARS](https://appeears.earthdatacloud.nasa.gov/): extract MODIS/VIIRS/SRTM subsets for a point or area, returns CSV/GeoTIFF.
- [NASA POWER](https://power.larc.nasa.gov/): solar and meteorology data for any lat/lon, simple REST API, ideal for agriculture and energy challenges.
- [FIRMS](https://firms.modaps.eosdis.nasa.gov/): active fire detections (MODIS and VIIRS), map, API and CSV.
- [Earth Observatory](https://earthobservatory.nasa.gov/): articles and images explaining Earth-science phenomena, good for storytelling.
- [Earth Information Center](https://science.nasa.gov/earth/earth-information-center/): visualizations of a changing planet.
- [NISAR mission](https://nisar.jpl.nasa.gov/) and [ASF DAAC](https://asf.alaska.edu/): synthetic aperture radar (SAR) data.

**Moon, Mars and planets**
- [Moon Trek](https://trek.nasa.gov/moon/) and [Mars Trek](https://trek.nasa.gov/mars/): web map portals with layers, elevation and 3D for the Moon and Mars.
- [LROC Quickmap](https://quickmap.lroc.asu.edu/): high-resolution lunar imagery and topography.
- [PDS (Planetary Data System)](https://pds.nasa.gov/): raw planetary mission data archive.
- [JPL Horizons](https://ssd.jpl.nasa.gov/horizons/): positions of Sun, Earth, planets and spacecraft at any time and place (ephemerides), with an API.
- [NASA Eyes](https://eyes.nasa.gov/) and [Solar System Treks](https://trek.nasa.gov/): 3D visualizations to borrow ideas from.

**Astrophysics**
- [IRSA](https://irsa.ipac.caltech.edu/): infrared archives (SPHEREx, WISE, Spitzer).
- [MAST](https://archive.stsci.edu/): Hubble, JWST, TESS, Kepler, Gaia mirror.
- [HEASARC](https://heasarc.gsfc.nasa.gov/): high-energy astrophysics.

**Human spaceflight and life sciences**
- [NASA Open Science Data Repository (OSDR)](https://osdr.nasa.gov/): spaceflight biology and physiology data (formerly GeneLab and LSDA).
- [NASA Technical Reports Server (NTRS)](https://ntrs.nasa.gov/): papers and reports, full-text search and API.
- [PSI (Physical Sciences Informatics)](https://www.nasa.gov/psi/): microgravity physical-science experiment data, including combustion.

**Space weather and the Sun**
- [DONKI](https://ccmc.gsfc.nasa.gov/tools/DONKI/): space weather events database with API (also on api.nasa.gov).
- [SDO](https://sdo.gsfc.nasa.gov/data/): Sun images.

## Space Agency Partner data

The 2026 partners are: Angola, Bahrain, Brazil (AEB), CSA (Canada), ESA (Europe), ISRO (India), ASI (Italy), JAXA (Japan), KASA (Korea), MBRSC (UAE), CONAE (Argentina), NASRDA (Nigeria), Paraguay, Senegal, Spain, Turkey and UK Space Agency. Judges are told that using partner data is encouraged. Each challenge page lists the partner resources that apply.

Brazilian teams: [INPE](https://www.gov.br/inpe/) data (CBERS, Amazon deforestation PRODES/DETER, BDQueimadas fires) counts as partner-adjacent and is highly relevant for Earth challenges.

## Traps that cost hours

- **Earthdata Login.** Create the account on Saturday morning, not when you need the file. Downloads via scripts need the token or `.netrc`.
- **File formats.** HDF5, NetCDF and GeoTIFF need libraries (`xarray`, `netCDF4`, `rasterio`, `h5py`). Prefer services that give you CSV, JSON or PNG (POWER, AppEEARS, FIRMS, GIBS, Giovanni) when the challenge allows it.
- **File size.** A single granule can be gigabytes. Use subsetting services (AppEEARS, Earthdata Search spatial/temporal filters, OPeNDAP) instead of raw downloads.
- **Rate limits.** api.nasa.gov demo key allows 30 requests/hour; a free personal key allows 1,000/hour.
- **Mock first.** Build the UI on a small static sample (one CSV, one PNG), ship it, then wire the live data. A demo with real-looking sample data beats a broken live fetch.
- **Cite everything.** The submission form has a required References field. Keep a `SOURCES.md` in your repo from the first hour and paste it at the end.
