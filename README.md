# Cryptocurrency Price Prediction

A comprehensive machine learning framework for cryptocurrency price prediction and backtesting. This project implements multiple predictive models to forecast cryptocurrency prices and includes robust backtesting capabilities to evaluate trading strategies.

## 🚀 Features

- **Multiple ML Models**: Support for ARIMA, LSTM, Random Forest, XGBoost, SARIMAX, and Orbit models
- **Cryptocurrency Support**: ETH/USD and BTC/USD (XBT/USD) pairs
- **Timeframes**: 1-hour and 1-day intervals
- **Backtesting Engine**: Integrated backtesting with customizable strategies
- **Technical Indicators**: RSI, MACD, and other technical analysis indicators
- **Data Sources**: BitMEX and CoinMarketCap data loaders
- **Configuration Management**: Hydra-based configuration system
- **Metrics & Evaluation**: Comprehensive performance metrics and reporting
- **Visualization**: Plotting capabilities for predictions and backtest results

## 🛠️ Installation

1. Clone the repository:
```bash
git clone https://github.com/tejbhakhar/cryptocurrency-price-prediction.git
cd cryptocurrency-price-prediction
```

2. Install dependencies:
```bash
pip install -r requirements.txt
```

## 📊 Usage

### Training a Model

To train a model, use the `train.py` script with Hydra configuration:

```bash
python train.py model=arima dataset_loader=Bitmex
```

Available models:
- `arima`
- `lstm`
- `random_forest`
- `xgboost`
- `sarimax`
- `orbit`

Available data loaders:
- `Bitmex`
- `CoinMarket`

### Backtesting

Run backtesting on trained models:

```bash
python backtester.py
```

## 🏗️ Project Structure

```
CryptoPredictions/
├── backtester.py              # Backtesting engine
├── train.py                   # Model training script
├── requirements.txt           # Python dependencies
├── path_definition.py         # Path utilities
├── backtest/                  # Backtesting strategies
│   └── strategies.py
├── configs/                   # Hydra configuration files
│   ├── hydra/
│   ├── logging.conf
│   └── dataset_loader/
├── data/                      # Sample cryptocurrency data
│   ├── ETHUSD-1d-data.csv
│   ├── ETHUSD-1h-data.csv
│   ├── XBTUSD-1d-data.csv
│   └── XBTUSD-1h-data.csv
├── data_loader/               # Data loading and preprocessing
│   ├── Bitmex.py
│   ├── CoinMarketDataset.py
│   ├── indicators.py
│   └── creator.py
├── factory/                   # Core components factory
│   ├── trainer.py
│   ├── evaluator.py
│   └── profit_calculator.py
├── metrics/                   # Performance metrics
│   └── metrics.py
├── models/                    # ML model implementations
│   ├── arima.py
│   ├── LSTM.py
│   ├── random_forest.py
│   ├── xgboost.py
│   ├── sarimax.py
│   └── orbit.py
└── utils/                     # Utility functions
    ├── reporter.py
    └── average_meter.py
```

## 📈 Models

### ARIMA (AutoRegressive Integrated Moving Average)
Statistical model for time series forecasting.

### LSTM (Long Short-Term Memory)
Deep learning model for sequence prediction.

### Random Forest
Ensemble learning method for regression.

### XGBoost
Gradient boosting framework.

### SARIMAX (Seasonal ARIMA with eXogenous variables)
Extended ARIMA model with seasonal components.

### Orbit
Bayesian time series forecasting model.

## 🔧 Configuration

The project uses Hydra for configuration management. Configuration files are located in `configs/hydra/`. Key configuration areas:

- **Model parameters**: `configs/hydra/model/`
- **Dataset settings**: `configs/hydra/dataset_loader/`
- **Training parameters**: `configs/hydra/train.yaml`
- **Backtesting settings**: `configs/hydra/backtest.yaml`

## 📊 Data

The project includes sample data for:
- ETH/USD 1-day and 1-hour intervals
- BTC/USD 1-day and 1-hour intervals

Additional data can be loaded using the provided data loaders for BitMEX and CoinMarketCap.

## 📈 Backtesting

The backtesting engine supports:
- Custom trading strategies
- Commission modeling
- Performance metrics calculation
- Result visualization
