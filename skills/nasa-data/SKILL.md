---
name: nasa-data
description: Gets real NASA data into a hackathon project fast (NASA Space Apps 2026). Use when the team says "where do I get the data", "download NASA data", "the download needs a login", "the file is huge", "HDF/NetCDF", or when the hackathon-mode Sat 19:00 checkpoint (live data wired) is coming. Prefers four sources that need no account (FIRMS, POWER, GIBS, api.nasa.gov), gives the exact URL and loading code per lane, and tells the team when to stop and ship with a curated sample instead.
---

# NASA Data

Goal: real NASA data on screen within one hour, without creating an account first. The project already works on `data/sample.json` (hackathon-mode rule); this skill swaps that sample for a real download or a live call. If the real source fights back for more than an hour, the sample stays and the submission says so.

## Step 1: find out what the screen needs (one message)

Ask, or read from `CHALLENGE.md` and the code:

1. Which challenge, and the one core feature that is already on screen.
2. The shape the screen expects: a table of points, a time series for one place, an image for a map, or a list of facts. Match the source to the shape, not the other way around.
3. Region and date range. A city and one year is enough for a demo; the whole planet since 2000 is not a hackathon dataset. If the challenge itself asks for decades (challenge 09 wants a fire calendar since the early 2000s), split it: demo the mechanics on the no-login week of data today, request the archive in parallel (see the login rows), and say in the submission which years the live demo covers.
4. Lane: Vite + React (fetch in the browser or at build time) or Python + Streamlit (download once, read with pandas).

## Step 2: pick the source, in this order

Start at the top. Move down only when the row above cannot produce the shape from Step 1.

| Need | Source | Login | Returns | URL to call |
| --- | --- | --- | --- | --- |
| Active fires, last 24 h to 7 days, per continent | **FIRMS static CSV** | No | CSV, one row per detection | `https://firms.modaps.eosdis.nasa.gov/data/active_fire/noaa-20-viirs-c2/csv/J1_VIIRS_C2_South_America_24h.csv` (also `_48h`, `_7d`, `Global`, `USA_contiguous_and_Hawaii`). MODIS: `https://firms.modaps.eosdis.nasa.gov/data/active_fire/modis-c6.1/csv/MODIS_C6_1_South_America_24h.csv` |
| Weather, solar, soil for any lat/lon, daily since 1981 | **NASA POWER** | No | JSON or CSV | `https://power.larc.nasa.gov/api/temporal/daily/point?parameters=T2M,PRECTOTCORR&community=AG&longitude=-46.63&latitude=-23.55&start=20250101&end=20251231&format=JSON` |
| Satellite imagery as a map layer or a single picture, any date | **GIBS** | No | PNG/JPEG tiles, or one PNG for a bounding box | Tiles: `https://gibs.earthdata.nasa.gov/wmts/epsg3857/best/MODIS_Terra_CorrectedReflectance_TrueColor/default/2025-09-01/GoogleMapsCompatible_Level9/{z}/{y}/{x}.jpg`. One image: `https://gibs.earthdata.nasa.gov/wms/epsg4326/best/wms.cgi?SERVICE=WMS&REQUEST=GetMap&VERSION=1.3.0&LAYERS=MODIS_Terra_CorrectedReflectance_TrueColor&FORMAT=image/png&CRS=EPSG:4326&BBOX=-30,-60,-10,-40&WIDTH=1024&HEIGHT=1024&TIME=2025-09-01` |
| Space pictures, Mars rover photos, asteroids, space weather, Earth from DSCOVR | **api.nasa.gov** | Free key, 1 minute | JSON | `https://api.nasa.gov/planetary/apod?api_key=DEMO_KEY`, `/mars-photos/api/v1/rovers/curiosity/photos`, `/neo/rest/v1/feed`, `/DONKI/FLR`, `/EPIC/api/natural` |
| Natural events (fires, storms, volcanoes) as a list with coordinates | **EONET** | No | JSON | `https://eonet.gsfc.nasa.gov/api/v3/events?category=wildfires&status=open` |
| Mission photos and video for storytelling | **images.nasa.gov** | No | JSON with asset links | `https://images-api.nasa.gov/search?q=apollo%2011&media_type=image` |
| Fires over a custom box or past dates, up to 5 days per call | **FIRMS area API** | Free MAP_KEY by email | CSV | `https://firms.modaps.eosdis.nasa.gov/api/area/csv/<MAP_KEY>/VIIRS_NOAA20_NRT/<west,south,east,north>/<days 1-5>/<YYYY-MM-DD>`. For past years use the `_SP` sources (`MODIS_SP` since 2000, `VIIRS_SNPP_SP` since 2012) and loop 5 days at a time |
| Years of fire history for one country (challenge 09 asks for this) | **FIRMS archive download** | Earthdata account, or a code sent to any email | One CSV per country, sensor and year (MODIS since Nov 2000, VIIRS NOAA-20 since Apr 2018) | `https://firms.modaps.eosdis.nasa.gov/download/`. Request MODIS and VIIRS for the same country and years; the file arrives by email in minutes to hours, so request it Saturday morning and demo on the static 7-day CSV until it lands |
| MODIS/VIIRS vegetation, land temperature, elevation for a point or polygon | **AppEEARS** | Earthdata account | CSV or GeoTIFF, by email when ready | `https://appeears.earthdatacloud.nasa.gov/` |
| Anything else in Earthdata (SAR, ocean, atmosphere granules) | **Earthdata Search** | Earthdata account | HDF, NetCDF, GeoTIFF, often gigabytes | `https://search.earthdata.nasa.gov/` |

Rules while picking:

- **The first four rows cover most challenges.** Fires (09), farms (07), trends (02), jukebox (14) and anything with a map background live there. Only go below the line if the challenge's Resources section names a dataset that lives nowhere else.
- **Login rows cost an hour before the first byte.** Earthdata needs account creation, email confirmation, a token or `.netrc`, and the download tool of the week. If the team is there on Saturday afternoon, one person creates the account while the rest keep building on the sample.
- **Pick a satellite that is still publishing.** FIRMS lists VIIRS Suomi-NPP coverage as ending on 2 November 2026, and its static CSVs now come back with a header and zero rows. Use NOAA-20 (`noaa-20-viirs-c2`/`J1_VIIRS_C2`) or MODIS (`modis-c6.1`/`MODIS_C6_1`) with the same `_24h`/`_7d` suffix. In general, a continent file with only a header or a few dozen rows is a sensor gap, not a bug in your code: switch sensor and try again.
- **Region and date live in the URL when the source allows it.** POWER takes lat/lon and start/end; GIBS takes a bounding box and a date. FIRMS static CSVs come per continent, so the cut to a country happens in your code, and a lat/lon box is not a country: the box `-74..-34` by `-34..5` holds Brazil plus Peru, Bolivia, Paraguay, Colombia, Venezuela and a slice of ocean. For a demo, pick a state or a city-sized box and label it as such on screen ("Mato Grosso: lon -62 to -50, lat -18 to -7"). An exact country outline needs a polygon (`geopandas` + a GeoJSON of borders); do that only if the map makes the leak visible.
- **Never call these from the browser with a key in the code.** `DEMO_KEY` and a FIRMS MAP_KEY both appear in the repo and the deployed bundle. For api.nasa.gov, `DEMO_KEY` is fine for a demo (30 calls per hour per IP). For FIRMS, download once with a script and commit the CSV, or call it from a serverless function.

## Step 3: download once, commit the file

Download on Saturday, commit the result under `data/`, and point the screen at the file. A live fetch is a second feature; build it only if the first one is deployed and the judges would notice the difference.

Shell, works for every CSV and JSON above:

```bash
mkdir -p data
curl -L -o data/fires.csv "https://firms.modaps.eosdis.nasa.gov/data/active_fire/noaa-20-viirs-c2/csv/J1_VIIRS_C2_South_America_24h.csv"
curl -L -o data/weather.json "https://power.larc.nasa.gov/api/temporal/daily/point?parameters=T2M,PRECTOTCORR&community=AG&longitude=-46.63&latitude=-23.55&start=20250101&end=20251231&format=JSON"
wc -l data/fires.csv   # a continent with under ~100 lines means an empty or stalled sensor feed, see Step 2
```

Keep the committed file under 5 MB so the repo and the deploy stay fast. The South America 24 h VIIRS file is about 10,000 rows and under 1 MB; the 7-day file is about 60,000 rows and just over 5 MB, so filter it to your box before committing:

```bash
python3 -c "
import csv,sys
r=csv.DictReader(open('data/fires_7d.csv')); w=csv.DictWriter(open('data/fires.csv','w'),r.fieldnames); w.writeheader()
w.writerows(x for x in r if -62<float(x['longitude'])<-50 and -18<float(x['latitude'])<-7)"
```

## Step 4: load it, per lane

**Lane A, Vite + React.** Put the file in `public/data/` and fetch it at runtime; no library for JSON, `papaparse` for CSV.

```js
const res = await fetch('/data/fires.csv');
const { data } = Papa.parse(await res.text(), { header: true, dynamicTyping: true });
const matoGrosso = data.filter(r => r.latitude > -18 && r.latitude < -7 && r.longitude > -62 && r.longitude < -50); // a box, not a border
```

POWER JSON: the values are at `json.properties.parameter.T2M`, an object keyed by `YYYYMMDD`. `-999` means missing; drop it before charting.

GIBS as a Leaflet layer, with a date the user can change:

```js
<TileLayer url={`https://gibs.earthdata.nasa.gov/wmts/epsg3857/best/MODIS_Terra_CorrectedReflectance_TrueColor/default/${date}/GoogleMapsCompatible_Level9/{z}/{y}/{x}.jpg`} maxZoom={9} attribution="NASA GIBS" />
```

**Lane B, Python + Streamlit.** `pandas` reads the CSV straight from disk or from the URL.

```python
import pandas as pd, requests
fires = pd.read_csv("data/fires.csv")
fires = fires[fires.latitude.between(-18, -7) & fires.longitude.between(-62, -50)]  # a box, not a border
per_day = fires.groupby("acq_date").size()
weather = requests.get(POWER_URL).json()["properties"]["parameter"]
t2m = pd.Series(weather["T2M"]).replace(-999, None)
t2m.index = pd.to_datetime(t2m.index)
st.map(fires.rename(columns={"latitude": "lat", "longitude": "lon"}))
st.bar_chart(per_day)
st.line_chart(t2m)
```

Add `xarray` and `netCDF4` only if an Earthdata granule is the one thing the challenge needs. Open it once, slice the region and dates, save a small CSV, and go back to the code above. Nobody should open a 2 GB file twice during a hackathon.

## Step 5: write it down

Append to `SOURCES.md` right away, one line per source: dataset name, the exact URL you called, the date you downloaded it, the license (NASA data is public domain unless the page says otherwise). The submission form's References field is required and this is where it comes from. Also note any sensor gap or date limit you worked around; the judges score honesty about scope under Relevance.

## When to stop

If by the hackathon-mode Sat 19:00 checkpoint the real source is still not on screen, stop. Keep the curated sample, make sure it is realistic (real column names, real value ranges, a real date), and write one sentence in the README and the submission: "Demo runs on a curated sample of <dataset>, downloaded on <date>; the live source is <URL>." Judges have seen a hundred broken live fetches and zero of them scored well.
