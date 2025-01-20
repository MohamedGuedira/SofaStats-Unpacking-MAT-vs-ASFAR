# Football Match Analysis: MAT vs ASFAR

This project analyzes the dynamics of a football match between Moghreb Atletico Tetouan (MAT) and ASFAR Rabat. Using Python and advanced football analytics libraries, the notebook scrapes match data, visualizes key metrics, and provides actionable insights on team performance and player contributions.

## Project Overview

The primary goal of this project is to leverage match data to:
- Understand momentum shifts during the game.
- Analyze team performance through possession, shots, and other metrics.
- Visualize player contributions using shot maps and heatmaps.

This project demonstrates essential skills for football analytics, including data scraping, visualization, and statistical analysis.

## Key Features

### Data Collection
- Utilized the `ScraperFC` library to extract match momentum, team statistics, and player actions from SofaScore.
- Focused on metrics such as ball possession, expected goals (xG), and shot types.

### Visualization
- Created interactive and visually appealing graphics with `mplsoccer`, such as:
  - Match momentum bars to illustrate game dynamics.
  - Shot maps showcasing goal attempts by location and type.
  - Heatmaps highlighting player activity zones.

### Insights
- Explored how team strategies influenced game momentum.
- Identified key players and their impact on the match.
- Compared performance metrics between MAT and ASFAR to highlight strengths and areas for improvement.

## Technical Details

### Tools and Libraries
- **Python Libraries:** `mplsoccer`, `ScraperFC`, `matplotlib`, `seaborn`, `pandas`, `numpy`.
- **Data Source:** SofaScore match page.

### Workflow
1. **Scraping Data:** Extracted match data, including momentum and player statistics.
2. **Data Cleaning:** Preprocessed data for analysis.
3. **Visualization:** Designed visual representations to highlight insights.
4. **Analysis:** Derived actionable insights from the visualized data.

### Key Code Snippets
#### Scraping Match Momentum:
```python
import ScraperFC as sfc
scraper = sfc.Sofascore()
match_momentum = scraper.scrape_match_momentum(
    'https://www.sofascore.com/fr/football/match/moghreb-atletico-tetuan-as-far-rabat/UMjsZax#id:13186583'
)
```

#### Visualizing Momentum Swings:
```python
import matplotlib.pyplot as plt
fig, ax = plt.subplots(figsize=(15, 5))
plt.bar(match_momentum_home.minute, match_momentum_home.value, color='blue', label='Home')
plt.bar(match_momentum_away.minute, -match_momentum_away.value, color='red', label='Away')
plt.title("Match Momentum")
plt.legend()
plt.show()
```

#### Generating a Shot Map:
```python
from mplsoccer import Pitch
pitch = Pitch()
fig, ax = pitch.draw(figsize=(10, 6))
team_shots = shotmap_filtered[shotmap_filtered['isHome']]
pitch.scatter(team_shots['x'], team_shots['y'], ax=ax, color='blue', label='Shots')
plt.title("Shot Map")
plt.legend()
plt.show()
```

## How to Run the Project

### Prerequisites
- Python 3.8 or higher.
- Required libraries: `mplsoccer`, `ScraperFC`, `matplotlib`, `pandas`, `seaborn`, `numpy`.

### Installation
1. Clone the repository:
   ```bash
   git clone https://github.com/MohamedGuedira/SofaStats-Unpacking-MAT-vs-ASFAR.git
   ```
2. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```

### Execution
1. Open the notebook in Jupyter:
   ```bash
   jupyter notebook MATvsASFAR_analysis.ipynb
   ```
2. Run the cells sequentially to generate insights and visualizations.

## Potential Extensions
- **Predictive Modeling:** Build a model to predict match outcomes based on momentum and key metrics.
- **Interactive Dashboards:** Use `Plotly` or `Dash` to make visualizations interactive.
- **Generalization:** Adapt the code to analyze other matches or leagues.

## About the Author
As a data scientist specializing in football analytics, I am passionate about leveraging data to uncover insights and support decision-making in sports. For inquiries or collaborations, please contact me at [guedirasimo0@gmail.com].

## Acknowledgments
- [SofaScore](https://www.sofascore.com) for match data.
- Open-source contributors to libraries like `mplsoccer` and `ScraperFC`. 
