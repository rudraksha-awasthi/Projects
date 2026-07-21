# 📈 Stock Price Prediction using LSTM

A deep learning model that predicts stock closing prices using historical data, built with PyTorch and an LSTM (Long Short-Term Memory) neural network.

## Overview

This project fetches historical stock price data via the Yahoo Finance API, preprocesses it into sequential time windows, and trains an LSTM model to predict the next day's closing price based on the previous 30 days of price movement.

## Features

- Fetches live historical stock data using `yfinance`
- Sequence-based data preparation (sliding window approach)
- LSTM-based neural network built with PyTorch
- Feature scaling with `StandardScaler` for stable training
- Train/test split evaluation using RMSE (Root Mean Squared Error)
- Visualization comparing actual vs. predicted prices

## Tech Stack

- **Python**
- **PyTorch** — model architecture and training
- **yfinance** — historical stock data
- **scikit-learn** — data scaling and evaluation metrics
- **pandas / numpy** — data handling
- **matplotlib** — visualization

## How It Works

1. **Data Collection** — Downloads historical closing prices for a given ticker (default: `AAPL`) starting from 2020.
2. **Preprocessing** — Scales the closing price data and splits it into overlapping 30-day sequences.
3. **Train/Test Split** — 80% of sequences used for training, 20% held out for testing.
4. **Model** — A 2-layer LSTM network (hidden size 32) followed by a fully connected layer to output a single predicted price.
5. **Training** — Trained for 200 epochs using MSE loss and the Adam optimizer.
6. **Evaluation** — Predictions are inverse-transformed back to actual price scale, then compared against real prices using RMSE.
7. **Visualization** — Plots actual vs. predicted prices over the test period.

## Setup & Usage

```bash
# Clone the repository
git clone https://github.com/your-username/stock-price-prediction.git
cd stock-price-prediction

# Create and activate a virtual environment
python3 -m venv venv
source venv/bin/activate      # Windows: venv\Scripts\activate

# Install dependencies
pip install -r requirements.txt

# Run the notebook
jupyter notebook
```

Open `stock_prediction.ipynb` and run all cells. Change the `ticker` variable to predict a different stock.

## Results

The model outputs a plot comparing actual vs. predicted closing prices on unseen test data, along with RMSE scores for both training and test sets.

## Disclaimer

This project is for educational purposes only and is **not intended as financial advice**. Stock price prediction is inherently uncertain, and this model does not account for real-world market factors like news events, earnings reports, or macroeconomic conditions.

## Future Improvements

- Add multiple features (volume, open/high/low) instead of closing price alone
- Experiment with GRU or Transformer-based architectures
- Hyperparameter tuning (sequence length, hidden size, learning rate)
- Deploy as an interactive web app (Streamlit)


<img width="1470" height="956" alt="Screenshot 2026-07-21 at 11 48 41 AM" src="https://github.com/user-attachments/assets/bc82c2fe-e1ee-478d-aaa7-87b541ba3691" />
<img width="1470" height="956" alt="Screenshot 2026-07-21 at 11 54 40 AM" src="https://github.com/user-attachments/assets/a4fc0001-2872-4c6b-92c2-1473a5637e59" />
<img width="1470" height="956" alt="Screenshot 2026-07-21 at 1 29 56 PM" src="https://github.com/user-attachments/assets/776a409d-c559-492f-90c7-605db5626961" />
<img width="1470" height="956" alt="Screenshot 2026-07-21 at 1 30 04 PM" src="https://github.com/user-attachments/assets/65cabeae-dad3-40fb-bac5-4ea8d4d55390" />


