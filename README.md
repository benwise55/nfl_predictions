# NFL Model Static Web Dashboard

This directory contains the standalone static web application for viewing game simulation predictions, win probabilities, and scoring breakdowns.

## Contents
- `index.html`: Fully self-contained static HTML page (HTML + CSS + vanilla JS) with embedded slate predictions, dynamic win probability bars, filters, and scoring breakdown modals.
- `predictions.json`: The raw pre-computed Monte Carlo simulation data for the current week's games.

## Local Preview
You can open `index.html` directly in any web browser, or serve it locally:

```bash
# Serve locally on port 8000
python3 -m http.server 8000 -d web
# Then open http://localhost:8000 in your browser
```

## How to Update Predictions
To regenerate predictions for the upcoming week and update the static site:

```bash
# 1. Run the simulation pipeline to generate predictions JSON
python3 scripts/generate_week_predictions.py

# 2. Build the static web page into web/index.html
python3 scripts/build_dashboard_html.py

# 3. Commit and push to GitHub
git add web/
git commit -m "Update weekly game predictions"
git push
```

