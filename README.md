
## City Vibe Analyzer

City Vibe Analyzer is a modular Python application that collects, analyzes, and visualizes city data to evaluate overall "city vibe".


✅ How to run the project (first time)

1️⃣ Clone the repo & go to the branch

Checkout branch: feat/cli-menu

2️⃣ Create & activate virtual environment

python -m venv .venv
source .venv/Scripts/activate   # Windows Git Bash
source .venv/Scripts/activate


3️⃣ Install dependencies

pip install -r requirements.txt


4️⃣ Install project as CLI

pip install -e .


This enables the command:
./.venv/Scripts/python.exe run.py --cli
PYTHONPATH=src ./.venv/Scripts/python.exe run.py --cli
PYTHONPATH=src ./.venv/Scripts/python.exe src/city_vibe/presentation/cli.py


city-vibe


5️⃣ Start the traffic mock API (IMPORTANT – separate terminal)

PYTHONPATH=src python src/city_vibe/clients/traffic/mock_api.py
Eller  
PYTHONPATH=src ./.venv/Scripts/python.exe src/city_vibe/clients/traffic/mock_api.py


Leave this terminal running.

6️⃣ (If you get any SQLite error – do this once)

rm -f data/city_analysis.db

(SQLite schema reset – normal in dev)

7️⃣ Start the application

city-vibe


8️⃣ Use the menu

Choose option 1 to analyze a city (e.g. Stockholm)

Option 2 to view latest analysis + recommendations

Plots & summaries are generated automatically

⚠️ Common notes

.db, plots, and summary files are local only (not pushed to GitHub)

If something feels broken → delete data/city_analysis.db and run again

Mock API must be running for traffic data

