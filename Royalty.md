
CatalogIQ — Music Catalog Investment Analyzer

A Flask-based web application that scores and rates music catalogs as investment assets using PSR (Price-to-Streams Ratio) analysis, streaming trend data, sync placement metrics, and revenue breakdown modeling.

Overview
CatalogIQ is a single-file Flask application that functions like a Bloomberg Terminal for music IP. It lets users browse and analyze artist catalogs album-by-album, generating investment verdicts based on a proprietary scoring model. Any artist not in the local database can be fetched live from the iTunes API, with financial metrics estimated from streaming data.
This tool is designed for music finance professionals, catalog investors, and anyone modeling royalty cash flows — similar in concept to tools used at firms like Primary Wave, HarborView Equity Partners, or Hipgnosis.

Features

PSR Scoring Engine — Scores each album 0–100 across four weighted dimensions: PSR multiple, 3-year stream trend, sync placements, and publishing/sync income share
Investment Verdicts — Returns actionable ratings: STRONG BUY, BUY, MONITOR, PASS, or STRONG PASS
Pre-loaded Artist Database — Includes curated data for 5 high-profile catalogs out of the box
Live iTunes Lookup — Search any artist not in the database; real album metadata is fetched and financial metrics are modeled deterministically
Album-Level Breakdown — Per-album view of PSR multiple, estimated annual revenue, sync placements, publishing/sync/recording income splits, and 3-year stream sparklines
Track Listing + Audio Previews — Expandable track lists with 30-second iTunes preview playback for each album
Indie vs. Major Label Tagging — Independent artists are flagged with ownership context
In-memory Caching — iTunes API responses are cached per session to minimize redundant requests
Cyberpunk UI — Dark terminal-style interface built with vanilla HTML/CSS/JS, fully embedded in the Python file


Pre-loaded Artists
ArtistGenreLabel StatusChance the RapperHip-Hop / Gospel Rap★ IndependentFrank OceanR&B / Neo-Soul★ IndependentHozierIndie Folk / Blues Rock★ IndependentTaylor SwiftPop / CountryMajor (Republic)Kendrick LamarHip-Hop / RapMajor (pgLang / Interscope)

Scoring Model
Each album is scored out of 100 across four factors:
FactorMax DeductionDescriptionPSR Multiple–40 ptsPrice-to-Streams ratio; lower is more attractive3-Year Stream Trend–30 ptsGrowth trajectory over the trailing 3 yearsSync Placements–15 ptsTV, film, and ad licensing activityPublishing + Sync Income %–15 ptsShare of revenue from high-margin income streams
Verdict thresholds:
ScoreVerdict78–100▲ STRONG BUY62–77▲ BUY48–61◆ MONITOR35–47▼ PASS0–34▼ STRONG PASS

Note: PSR multiples and revenue figures for live iTunes lookups are modeled estimates derived from track count, release age, and genre-based revenue splits. They are not sourced from DSP analytics and should be verified before making investment decisions.


Tech Stack

Backend: Python 3, Flask
Data Source: iTunes Search API (no API key required)
Frontend: Vanilla HTML/CSS/JavaScript (embedded in Python as a template string)
Fonts: Orbitron, Rajdhani, Share Tech Mono (Google Fonts)
No external JS frameworks or databases required


Installation
1. Clone the repository
bashgit clone https://github.com/your-username/catalogiq.git
cd catalogiq
2. Install dependencies
bashpip install flask
3. Run the app
bashpython Royalty.py
4. Open in your browser
http://localhost:5050
To run on a different port, set the PORT environment variable:
bashPORT=8080 python Royalty.py

API Endpoints
MethodEndpointDescriptionGET/Serves the frontend UIGET/api/artistsReturns all pre-loaded artists with scores and verdictsGET/api/artist/<key>Returns full album breakdown for a pre-loaded artistGET/api/search?q=<query>Searches pre-loaded artists by name or genreGET/api/lookup?name=<name>Looks up any artist via iTunes (falls back to pre-loaded data)GET/api/album_tracks?id=<itunes_id>Returns track listing for an album by iTunes collection IDGET/api/album_tracks_by_name?artist=<name>&album=<title>Returns track listing by artist and album name

Project Structure
Royalty.py          # Entire application — backend + frontend in one file
README.md
Everything — Flask routes, scoring logic, artist data, and the full HTML/CSS/JS UI — lives in a single file for easy deployment.

Use Cases

Portfolio screening — Quickly rank catalogs by investment attractiveness
Catalog due diligence — Drill into album-level PSR, sync exposure, and revenue mix before acquisition
Educational — Understand how streaming metrics translate to catalog valuations
Music finance portfolio projects — Demonstrable tool for roles at music investment firms, royalty funds, and entertainment-focused PE shops


Limitations & Disclaimers

Revenue and PSR figures for iTunes-sourced artists are modeled estimates, not real financial data
Streaming figures are not pulled from Spotify, Apple Music, or any DSP — monthly stream estimates are algorithmically derived
This tool is intended for educational and analytical purposes only — not investment advice
iTunes API availability may affect live lookup functionality


Future Improvements

 Spotify API integration for real monthly listener and stream data
 Exportable PDF/CSV reports per artist
 Comparable transaction database (catalog deal multiples)
 Discounted Cash Flow (DCF) module with adjustable discount rates
 User-editable artist and album entries
 Persistent storage (SQLite or PostgreSQL backend)


Author
Built by Dhruva — Financial Technology student, Fund Analyst, and music finance enthusiast.
