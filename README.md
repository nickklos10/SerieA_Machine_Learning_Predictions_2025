# Serie A Machine Learning Predictions

This project involves scraping, cleaning, and analyzing Serie A soccer data, including team statistics, player transfers, and manager details, to build machine learning models predicting various outcomes. The models predict team points, goals, wins, draws, losses, and final rankings.

## Table of Contents

- [Installation](#installation)
- [Scripts Overview](#scripts-overview)
- [Technologies Used](#technologies-used)
- [Repository Structure](#repository-structure)
- [Setup Instructions](#setup-instructions)
- [Usage](#usage)
- [Database Setup](#database-setup)
- [User Roles and Permissions](#user-roles-and-permissions)
- [Contributing](#contributing)
- [License](#license)
- [Contact](#contact)


## Installation

1. Clone the repository:
```
git clone https://github.com/yourusername/SerieA_Machine_Learning_Predictions.git
cd SerieA_Machine_Learning_Predictions
```

2. Install required dependencies:
```
pip install -r requirements.txt
```

3. Ensure all CSV data files are in place and correctly formatted.


## Scripts Overview

- Transfer_SerieA_scraping.ipynb: Scrapes transfer data for Serie A teams, including player names, ages, nationalities, positions, market values, and transfer fees. Saves data as serie_a_transfers.csv.

- Teams_SerieA_scraping.ipynb: Extracts match and team performance data for Serie A teams from multiple seasons. Saves team-specific CSV files.

- SerieA_Team_Stats.ipynb: Scrapes team statistics from Transfermarkt, such as squad size, average age, market values, and total value. Saves the final dataset as serie_a_market_values.csv.

- ML_SerieA_Ultimate_DF.ipynb: Cleans and aggregates all scraped data into a unified DataFrame, applies data transformations, and prepares it for machine learning modeling.

- Serie_A_Managers.ipynb: Scrapes manager data for Serie A teams, including matches managed, seasons, titles, and points per match (PPM). Saves the data as serie_a_coaches.csv.

- Serie_A_ML_Final.ipynb: Builds and trains a machine learning model using neural networks to predict team performance metrics, including points, victories, goals scored, goals conceded, and final standings.

