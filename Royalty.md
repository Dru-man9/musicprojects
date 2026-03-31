Music Catalogue Investment Analyzer
A Python tool that analyzes music artists' streaming performance and estimated royalty rates to identify promising investment opportunities in catalogues and albums.

Think like a catalogue fund manager. Explore who's worth backing before the market does.


🎵 What This Tool Does
The Music Catalogue Investment Analyzer combines real streaming data with financial analysis to help you understand music catalogue valuations the way industry professionals do. Whether you're curious about how A&R teams scout talent, how catalogue funds identify acquisition targets, or simply want to explore the economics of music—this tool lets you explore both.

Pulls artist streaming data across platforms (Spotify, etc.)
Calculates PSR (Performance & Streaming Royalty) rates to estimate per-stream earning potential
Surfaces high-potential artists whose catalogues may be undervalued or ready for acquisition
Visualizes financial trends across streaming metrics, growth rates, and revenue potential
Simulates catalogue valuation using multiple methods (DCF, revenue multiples, comparable artist analysis)


🎯 Who Is This For?

Music Finance & Investment: Catalogue fund managers, entertainment lawyers, and investment professionals exploring valuation methodologies
A&R & Talent Scouts: Anyone thinking about artist development and long-term revenue potential
Music Fans & Finance Enthusiasts: People who want to understand the business of music and explore it hands-on
Students & Educators: Learn how entertainment finance, data analytics, and investment thinking intersect


🚀 Quick Start
Prerequisites

Python 3.8+
pip (Python package manager)
API keys for data sources (see Configuration below)

Installation
bash# Clone the repository
git clone https://github.com/your-username/music-catalogue-analyzer.git
cd music-catalogue-analyzer

# Create a virtual environment (recommended)
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate

# Install dependencies
pip install -r requirements.txt

# Set up your environment variables
cp .env.example .env
# Edit .env with your API keys
Run the Application
bashpython app.py

