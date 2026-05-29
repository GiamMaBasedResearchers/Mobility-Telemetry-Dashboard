Mobility Telemetry Dashboard - Visualizer & OSINT

Obviously, there will be several fixes to be made, and the code isn't clean, and you will find entities that appear to be false positives but are not always false positives. I consider the exercise very interesting for various levels of understanding, knowledge and technicalities.

As always, you can use the plain HTML locally 👋👋👋

To preview GitHub HTML files, use these services by pasting the links:

https://raw.githack.com/ (Tested / working)

Fast Link:

- https://raw.githack.com/GiamMaBasedResearchers/Mobility-Telemetry-Dashboard/main/Mobility%20Telemetry%20Dashboard.html

Thanks to:

https://github.com/neoascetic/rawgithack

You can also use W3Schools Tryit Editor:

https://www.w3schools.com/html/tryit.asp?filename=tryhtml_default


A lightweight, single-file HTML web-based dashboard designed for visualizing, extracting, and performing OSINT (Open Source Intelligence) analysis on mobility data feeds. This tool supports the GBFS (General Bikeshare Feed Specification) standard and is capable of mapping raw telemetry data, including uORB/MAVlink structures.


<img width="1918" height="923" alt="image" src="https://github.com/user-attachments/assets/5d0dac53-487b-43eb-9496-b6d89f322fe1" />



🚀 Features

Interactive Map Visualization: Real-time mapping of stations, vehicles, and telemetry using Leaflet.js.

GBFS JSON Feed Support: Fully compatible with standard GBFS feeds, handling station_information, free_bike_status, and geofencing_zones.
Auto-Merge Logic: Automatically combines status feeds with information feeds to display battery levels and station capacities.
Data Extraction: Includes a curated list of feeds (e.g., from transport.data.gouv.fr) and a manual input for custom URLs.
Metadata Inspector: View raw JSON snippets and detailed metadata for any point on the map.
No Backend Required: Runs entirely client-side (browser-based).

📖 How to Use & How It Works

Installation: Simply save the code as an .html file (e.g., dashboard.html) and open it in any modern web browser.

Select a Data Source:

Favorites: Quick access to common feeds (MEVO, Vilnius, Paris, NYC).
Gouv.fr Transport Data: A hardcoded section containing direct links extracted from the French transport portal.
Global Database: Imports the official MobilityData systems list via GitHub.
URL & Proxy: Paste any direct JSON link. Use a CORS proxy (like corsproxy.io) if the feed blocks browser requests.
Load Data: Click "Load" on a list item to fill the URL field, then click "Download Data".
Visualization: The dashboard will parse the JSON, drop markers on the map (color-coded by battery level if available), and populate the stats bar.


🤖 Smart Extractor (Theoretical Implementation)

The dashboard includes a Smart Extractor feature designed to simulate automated feed discovery.

Logic: It attempts to find open endpoints by constructing common URL patterns derived from Google Dorking techniques.
Dorks Referenced: The logic mimics searches for patterns such as:

inurl:json inurl:station_information
inurl:json inurl:GBFS
GBFS JSON inurl:json

Note: This feature works by trying to guess standard file paths (/gbfs.json, /v3/gbfs.json) based on a domain input. While effective for standard-compliant systems, it is limited when endpoints use obfuscated routing.


📚 Online Portals & Data Sources

This dashboard aggregates data from various open transport portals. Users can use these platforms to find new feeds to test in the manual input section:

France: https://transport.data.gouv.fr
Global Directory: https://mobilitydatabase.org
European Union: https://data.europa.eu

Example Datasets

To test the dashboard, you can try these specific feeds (paste them into the "URL & Proxy" section):

Chicago (USA): https://gbfs.divvybikes.com/gbfs/2.3/gbfs.json
Madrid (Spain): https://madrid.publicbikesystem.net/customer/gbfs/v2/gbfs.json


⚙️ Technical Specifications & Validation

Standard: GBFS (General Bikeshare Feed Specification).
Validator: To validate the structure of feeds used in this tool, refer to the official validator: https://github.com/MobilityData/gbfs-validator.
Telemetry Support (uORB/MAVlink): Beyond standard GBFS, the dashboard includes logic to map raw telemetry objects. It recognizes coordinate fields often found in drone/UAV protocols like uORB and MAVlink, specifically handling VehicleStatus messages:
Reference: https://docs.px4.io/main/en/msg_docs/VehicleStatus


⚠️ Disclaimer

Disclaimer: The code is for educational, training, analysis, & security purposes, & is intended for understanding & knowledge. The authors assume no liability for the misuse of this tool or the data it visualizes. Always ensure you have permission to access and visualize telemetry data.

👥 Credits

This code is provided by: "GiamMa-based researchers SDR R&D IoT"
Follow: @GiammaIoT2
