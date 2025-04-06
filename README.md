![image](https://github.com/user-attachments/assets/572c8da5-5014-4fd2-afa9-2843fa35f60b) 
# Serie A Machine Learning Predictions

This project involves scraping, cleaning, and analyzing Serie A soccer data—including team statistics, player transfers, and manager details—to build machine learning models that predict various outcomes. The models forecast team points, wins, draws, losses and final standings for the 2024/2025 season.

## Table of Contents

- [Installation](#installation)
- [Scripts Overview](#scripts-overview)
- [Technologies Used](#technologies-used)
- [Data Preparation](#data-preparation)
- [Modeling](#modeling)
- [SHAP Analysis](#shap-analysis)
- [Dataset](#dataset)
- [Result](#result)
- [Data Sources](#data-sources)
- [Predicted Standings](#predicted-standings)

## Installation

1. Clone the repository:
```
git clone https://github.com/nickklos10/SerieA_Machine_Learning_Predictions.git
cd SerieA_Machine_Learning_Predictions_2025
```

2. Install required dependencies:
```
pip install -r requirements.txt
```

3. Ensure all CSV data files are in place and correctly formatted.


## Scripts Overview

- `Transfer_SerieA_scraping.ipynb`: Scrapes transfer data for Serie A teams, including player names, ages, nationalities, positions, market values, and transfer fees. Saves data as serie_a_transfers.csv.

- `Teams_SerieA_scraping.ipynb`: Extracts match and team performance data for Serie A teams from multiple seasons. Saves team-specific CSV files.

- `SerieA_Team_Stats.ipynb`: Scrapes team statistics from Transfermarkt, such as squad size, average age, market values, and total value. Saves the final dataset as serie_a_market_values.csv.

- `ML_SerieA_Ultimate_DF.ipynb`: Cleans and aggregates all scraped data into a unified DataFrame, applies data transformations, and prepares it for machine learning modeling.

- `Serie_A_Managers.ipynb`: Scrapes manager data for Serie A teams, including matches managed, seasons, titles, and points per match (PPM). Saves the data as serie_a_coaches.csv.

- `2025_Final_ML_SerieA.ipynb`: Builds and trains a machine learning model using neural networks to predict team performance metrics, including points, victories, ties, losses and final standings.
  
> [!NOTE]
> `Recent Modifications:`
>  * Improved the prediction pipeline with enhanced imputation, scaling, and updated categorical encoding.
>  * Adjusted the post‑processing step to ensure that the predicted outcomes (wins, draws, and losses) are consistent with the predicted points.


## Technologies Used

- `Python 3.9`
- `Pandas` for data manipulation.
- `Requests` and `BeautifulSoup` for web scraping.
- `Scikit-learn` for scaling, imputation and evaluation metrics.
- `TensorFlow/Keras` for machine learning modeling.
- `SHAP` for model explainability and feature importance.


## Data Preparation

### Adding Scraped CSV Files
In order to use the data aggregation and preparation script (ML_SerieA_Ultimate_DF.ipynb), ensure that all scraped CSV files are present in the same directory as the notebook. These CSV files include:

- Transfer data from `Transfer_SerieA_scraping.ipynb`.
- Team-specific data from `Teams_SerieA_scraping.ipynb`.
- Team stats data from `SerieA_Team_Stats.ipynb`.
- Manager data from `Serie_A_Managers.ipynb`.
  
The script aggregates these files, cleans the data, and prepares a unified dataset for machine learning modeling.

Make sure the following CSV files are available:

- `serie_a_transfers[year].csv`
- `scraped_data_[TeamName].csv`
- `serie_a_market_values.csv`
- `serie_a_coaches_grouped.csv`
  
Run `ML_SerieA_Ultimate_DF.ipynb` to combine these into a final dataset.

### Adding the Final Aggregated File
After running `ML_SerieA_Ultimate_DF.ipynb`, the script will generate an aggregated file called `final_merged_data_with_transfers.csv`, which contains all the combined data for model training.

To proceed with building and training the machine learning models, ensure that this final file is placed in the same directory as the `Serie_A_ML_Final.ipynb` script. This file is essential as it contains the preprocessed data used for predictions in the final model.


## Modeling

The model uses a neural network with multiple input features, such as:

* Numerical Inputs: Squad size, average age, market values, etc. (including log-transformed versions)
* Categorical Inputs: Team and coach (encoded to handle unknown values)
* Other Inputs: Total games played (Gio)

> [!NOTE]
> `Modifications:` The prediction pipeline was updated to include improved imputation, scaling, and robust post‑processing (adjusting wins, draws, and losses so that they sum to a realistic season total based on the predicted points).



## SHAP Analysis

The SHAP library is used to analyze the impact of features on predictions. Important features like team market value, manager, and transfer fees are visualized to understand how they influence team performance predictions.


## Dataset

The datasets are aggregated from multiple sources:

- `Serie A transfers`: Player movement in and out of teams.
- `Team statistics`: Squad size, age, foreigners, market value.
- `Manager data`: Manager history for each club.
- `Team performance`: Wins, draws, losses, goals for, goals against.

## Results
The machine learning model predicts the final standings for the 2024/2025 Serie A season, including estimates for team points, wins, draws, losses, and overall rankings. Detailed analysis identifies overachieving and underachieving teams based on historical performance and current market values.

<details> <summary><strong>Spoiler: Inter Milan Will Be Back-to-Back Champions!</strong></summary>
According to our model predictions, Inter Milan is expected to win the Serie A title for the 2024/2025 season, marking their second consecutive championship. The model’s forecasts, supported by key factors such as team market value and transfer activity, strongly indicate Inter's dominance in the upcoming season.

</details>
The complete predicted standings, along with SHAP and dependence plots illustrating feature importance, are included in this repository.

## Data Sources
The data for this project was scraped from the following websites:

- [Transfermarkt](https://www.transfermarkt.us/): This website provides detailed soccer statistics, including player transfers, team statistics, and manager performance data. It was used to scrape information on player transfers, team market values, and manager history.

- [Italia1910](http://www.italia1910.com/): This website provides historical Serie A standings and match data. It was used to scrape team-specific performance data for various Serie A seasons.

> [!IMPORTANT]
> These sources provided all the necessary data to build a comprehensive dataset for the machine learning models. Make sure to review the terms of service for these 
> websites if you plan to use them for further data collection.

## Predicted Standings

![Screenshot 2025-01-23 at 6 52 05 PM](https://github.com/user-attachments/assets/6ea86563-d3ad-4276-ab97-9b7664e6eeda)


