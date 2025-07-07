# Formula 1 Race Winner Prediction

This project uses machine learning to predict the winner of Formula 1 races based on historical data from the "Formula 1 World Championship (1950–2024)" dataset. The model leverages features like qualifying position, driver form, and track-specific win rate to make predictions using a Random Forest Classifier. The project includes comprehensive evaluation metrics (accuracy, precision, recall, F1-score, ROC-AUC, log loss) and visualizations like feature importance, confusion matrix, and ROC curve.

## Table of Contents
- [Project Overview](#project-overview)
- [Dataset](#dataset)
- [Installation](#installation)
- [Usage](#usage)
- [Project Structure](#project-structure)
- [Features](#features)
- [Evaluation Metrics](#evaluation-metrics)
- [Future Improvements](#future-improvements)
- [Contributing](#contributing)
- [License](#license)

## Project Overview
Formula 1 is a data-rich sport with decades of race results, qualifying data, and driver performance metrics. This project builds a predictive model to determine the likelihood of a driver winning a race, focusing on the 2024 season for testing. The model uses historical data (2010–2022) to train and evaluates performance with multiple metrics to ensure robustness.

The project is implemented in a Jupyter Notebook, making it easy to explore, modify, and visualize results interactively.

## Dataset
The project uses the ["Formula 1 World Championship (1950–2024)" dataset](https://www.kaggle.com/datasets/rohanrao/formula-1-world-championship-1950-2020) from Kaggle, compiled from the [Ergast API](http://ergast.com/mrd/). Key files used:
- `results.csv`: Race results with driver positions.
- `races.csv`: Race details (e.g., year, circuit).
- `drivers.csv`: Driver information (e.g., names).
- `qualifying.csv`: Qualifying positions for each race.

**Note**: You must download the dataset from Kaggle and place the CSV files in a `data` folder in the project directory.

## Installation
1. **Clone the Repository**:
   ```bash
   git clone https://github.com/AwaisKhan-01/F1-Race-and-Championship-Predictor.git
   cd your-repo-name
   ```

2. **Install Dependencies**:
   Ensure you have Python 3.8+ installed. Install the required libraries using pip:
   ```bash
   pip install pandas numpy scikit-learn matplotlib seaborn
   ```

3. **Download the Dataset**:
   - Download the Kaggle dataset from [here](https://www.kaggle.com/datasets/rohanrao/formula-1-world-championship-1950-2020).
   - Extract the CSV files (`results.csv`, `races.csv`, `drivers.csv`, `qualifying.csv`) into a `data` folder in the project root.

4. **Set Up Jupyter Notebook**:
   Ensure Jupyter is installed:
   ```bash
   pip install jupyter
   ```
   Launch Jupyter Notebook:
   ```bash
   jupyter notebook
   ```

## Usage
1. **Open the Notebook**:
   Open `f1_winner_prediction.ipynb` in Jupyter Notebook.

2. **Run the Cells**:
   The notebook is divided into five cells:
   - **Cell 1**: Imports libraries and sets up the environment.
   - **Cell 2**: Loads and merges data from the Kaggle dataset.
   - **Cell 3**: Creates features (e.g., driver form, track win rate, qualifying position).
   - **Cell 4**: Trains a Random Forest Classifier and evaluates it with multiple metrics.
   - **Cell 5**: Predicts win probabilities for a sample 2024 race.

3. **Expected Outputs**:
   - Data tables showing raw and processed data.
   - Model accuracy, precision, recall, F1-score, ROC-AUC, and log loss.
   - Visualizations: feature importance, confusion matrix, and ROC curve.
   - Predicted win probabilities for a sample race (e.g., Bahrain Grand Prix).

4. **Customize**:
   - Change the `year` variable (e.g., to 2022) to predict for other seasons.
   - Modify features in `create_features` to include additional data (e.g., team performance).

## Project Structure
```
F1-Race-and-Championship-Predictor
├── data/
│   ├── results.csv
│   ├── races.csv
│   ├── drivers.csv
│   ├── qualifying.csv
├── f1_winner_prediction.ipynb
├── README.md
```

## Features
The model uses the following features to predict race winners:
- **Qualifying Position**: Starting grid position for the race.
- **Driver Form**: Average finishing position in the driver’s last 5 races.
- **Track Win Rate**: Proportion of wins on the specific track in prior years.

## Evaluation Metrics
The model is evaluated using:
- **Accuracy**: Proportion of correct predictions.
- **Precision**: Proportion of predicted winners who actually won.
- **Recall**: Proportion of actual winners correctly predicted.
- **F1-Score**: Harmonic mean of precision and recall.
- **ROC-AUC**: Measures the model’s ability to distinguish winners from non-winners.
- **Log Loss**: Penalizes incorrect probabilities.
- Visualizations include a confusion matrix and ROC curve for deeper insights.

## Future Improvements
- Add more features (e.g., team performance, weather data).
- Experiment with other models (e.g., Logistic Regression, XGBoost).
- Extend predictions to podium finishes or lap times.
- Incorporate real-time data for 2024+ races.

## Contributing
Contributions are welcome! To contribute:
1. Fork the repository.
2. Create a new branch (`git checkout -b feature/your-feature`).
3. Make changes and commit (`git commit -m "Add your feature"`).
4. Push to your branch (`git push origin feature/your-feature`).
5. Open a pull request.

Please ensure your code follows PEP 8 guidelines and includes comments for clarity.

## License
This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.
