🌆 City Vibe Analyzer

City Vibe Analyzer is a Python-based CLI application that bridges the gap between objective weather data and subjective urban experience.
Instead of only showing numbers such as temperature or congestion, the system analyzes and translates data into an understandable “city vibe” with visualizations and human-oriented recommendations.

The project demonstrates how raw data can be collected, analyzed, stored, visualized, and presented in a user-friendly way through a complete automated pipeline.

✨ Project Idea

Weather applications often provide numbers without context.
City Vibe Analyzer answers a different question:

How does a city actually feel today?

By combining:

meteorological data (weather),

simulated traffic data,

rule-based analysis,

and human-readable recommendations,

the project helps users understand the atmosphere of a city, not just its statistics.

🧠 Key Features

Interactive CLI menu

Automatic geocoding (city name → latitude/longitude)

Weather data fetched from Open-Meteo API

Traffic data via a local mock API (Flask)

Rule-based analysis and city status classification

SQLite database for persistence

Data visualizations using matplotlib

Human-friendly recommendations loaded from a JSON configuration

Fully testable with pytest

Clean project structure using src/ layout

🏗️ Project Structure
city-analysis/
├── src/
│   └── city_vibe/
│       ├── analysis/        # Metrics and rule-based analysis
│       ├── clients/         # Weather, traffic, geocoding clients
│       ├── presentation/    # CLI, plots, user interaction
│       ├── storage/         # Database repository logic
│       ├── database.py      # SQLite setup and helpers
│       └── __main__.py      # CLI entrypoint
├── tests/                   # Pytest test suite
├── data/
│   └── comments.json        # Recommendation text configuration
├── reports/
│   ├── plots/               # Generated charts (ignored by git)
│   └── summary/             # Generated summaries (ignored by git)
├── requirements.txt
├── pyproject.toml
└── README.md

🚀 How to Run the Project
1️⃣ Create and activate a virtual environment
python -m venv .venv


Activate it:

Windows (Git Bash):

source .venv/Scripts/activate

2️⃣ Install dependencies
pip install -r requirements.txt

3️⃣ Install the project as a CLI tool
pip install -e .


This creates the command:

city-vibe

4️⃣ Start the traffic mock API (separate terminal)
PYTHONPATH=src python src/city_vibe/clients/traffic/mock_api.py


The mock server runs at:

http://127.0.0.1:5001

5️⃣ Start the application
city-vibe

🧭 CLI Menu Overview
1) Sense the city (analyze current vibe)
2) View latest vibe analysis (from DB)
3) List saved cities (from DB)
4) List recent runs (from DB)
5) Re-generate plots (from DB data)
6) Database info
7) Exit

Menu explanation (non-technical)

Sense the city: analyzes a city’s current atmosphere

View latest analysis: shows the most recent stored result

List saved cities: displays cities already analyzed

Recent runs: shows recent analysis history

Re-generate plots: recreates charts from stored data

Database info: system and storage overview

📊 Output

Plots are saved in reports/plots/

Summaries are saved in reports/summary/

Both folders contain generated files and are ignored by Git

🧪 Testing

Run the full test suite with:

PYTHONPATH=src pytest


Tests include:

analysis logic

database operations

geocoding client (mocked API calls)

repository layer

🗄️ Data Persistence

The application uses SQLite for local storage:

cities

weather data

traffic data

analysis results

The database file is created automatically and is not version-controlled.

🎓 Educational Purpose

This project was developed as part of a software development course and demonstrates:

Python project structuring

API integration

CLI design

Data analysis

Visualization

Database usage

Testing and debugging

Version control best practices

Separation of logic and content

🌱 Future Improvements

Replace mock traffic API with a real traffic data source

Add argparse subcommands for full automation

Extend recommendation logic with machine learning

Support multiple languages in recommendations


If you get a SQLite schema error (e.g. missing column), delete data/city_analysis.db and rerun the app.
rm -f data/city_analysis.db


“Eftersom SQLite inte uppdaterar tabeller automatiskt hanterar vi schemaändringar genom att återskapa databasen i utveckling, och strukturen kan enkelt utökas med migrations vid behov.”
