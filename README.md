# AI Car Price Predictor


## Overview
A simple web application that predicts used car prices from features (brand, model, year, mileage, fuel type, transmission, power). Train a model using a public dataset (Kaggle / CarDekho / Used Cars) and deploy a Flask app.


## Quick start
1. Clone repo
2. Put dataset CSV in `data/` (see below)
3. `pip install -r requirements.txt`
4. Edit `model_training.py` dataset_path variable if needed
5. Run `python model_training.py` to train and produce `model.pkl` and `dv.pkl`
6. Run `python app.py` and open `http://127.0.0.1:5000`


## Dataset
Use any used car price dataset from Kaggle (CarDekho / UsedCars). The training script expects at least these columns:
- `price` (target)
- `brand` (string)
- `model` (string)
- `year` (int)
- `km_driven` or `mileage` (numeric) — script uses `mileage` or `km_driven`
- `fuel_type` (string)
- `transmission` (string) e.g., Manual/Automatic
- `power` (numeric, optional)


If columns differ, adjust `model_training.py` mapping.


## Deployment
- Render / Railway / Heroku (small changes: set `PORT` env var and use `gunicorn`)
- For HuggingFace Spaces use `app.py` as Streamlit or Gradio instead (optional)