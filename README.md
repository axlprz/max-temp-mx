# Maximum Average Temperature Prediction for Mexican States Using KAN

This project implements a Kolmogorov-Arnold Network (KAN) to predict the average maximum temperature for Mexican states during the first half of 2028.

---

## Project Structure

```text
kan_temperature_prediction/
├── data/
│   ├── raw/             # Original files downloaded from SMN
│   │   ├── climate_2014_01.xlsx
│   │   └── ...
│   └── processed/       # Consolidated and cleaned data
│       └── climate2.xlsx
├── src/          
│   └── MaxTemp_KAN.py
├── models/              # Trained models
│   └── kan_model.pkl
├── assets/              # Plots and figures
│   ├── statistical_summary.png
│   ├── correlation_matrix.png
│   └── tmax_2028_map.png
├── docs/                # Documentation and references
│   └── ProyectoFinal_MODELOS.pdf
├── requirements.txt
├── README.md
└── .gitignore
```

---

## Data Sources

- **Servicio Meteorológico Nacional (SMN)**: Monthly maximum temperature summaries by state (2014–2024).
- **INEGI**: State population data (up to 2020).
- **Liu et al. KAN: Kolmogorov-Arnold Networks** (arXiv:2404.19756).
- **ProjectFinal_MODELOS.pdf**: Final project specification.

---

## Methodology

1. **Data Collection**  
   - Downloaded 131 monthly datasets from SMN (2014–2024).
2. **Preprocessing**  
   - Merged raw files into `climate2.xlsx`.  
   - Removed unnecessary columns (e.g., Station ID).  
   - Label-encoded the `State` column and normalized numerical features.  
   - Split data into training (2014–2022), validation (2023), and test (2024).
3. **Exploratory Analysis**  
   - Computed descriptive statistics for Tmax.  
   - Visualized temporal trends and distributions.  
   - Created a correlation matrix.  
   - Generated a geographical heatmap of maximum temperatures.
4. **Model Development**  
   - Defined KAN architecture with a trainable activation function.
5. **Training**  
   - Calibrated activation parameters on training data.
6. **Evaluation**  
   - Measured performance using Mean Absolute Error (MAE) on the test set.
7. **2028 Predictions**  
   - Predicted average Tmax for January–June 2028 for selected states.

---

## Results

- **Test MAE**: X.X °C  
- **States Analyzed**: Estado de México, CDMX, Jalisco, Veracruz, Puebla, Guanajuato, Nuevo León  
- **Average Predicted Tmax (Jan–Jun 2028)**: See `MaxTemp_KAN.py`

---

## Getting Started

```bash
git clone https://github.com/yourusername/kan_temperature_prediction.git
cd kan_temperature_prediction
pip install -r requirements.txt
jupyter notebook notebooks/
```

---

## Future Work

- Incorporate precipitation and humidity variables.  
- Add climate indices (e.g., ENSO, NAO).  
- Increase spatial granularity using city coordinates.  
- Explore hybrid KAN + deep learning architectures.

---

## References

1. Liu, Z. et al. KAN: Kolmogorov-Arnold Networks. arXiv:2404.19756  
2. SMN – Monthly weather summaries.  
3. INEGI – Population by state.  
4. Project specification document.
