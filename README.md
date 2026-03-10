# KrishiSevak - Crop Yield Optimization for Indian Agriculture

India has 150M+ farming households. Most use traditional methods passed down through generations - which worked fine until climate patterns started shifting. This project tries to bridge the gap between agricultural data science and what a farmer in rural India can actually use.

## Two parts to this project

### 1. The ML side (Jupyter notebook)

`Agriculture.ipynb` contains the data analysis and modeling work:

- Loaded historical crop yield data across Indian states (production volumes, area under cultivation, seasonal patterns)
- Explored which crops perform best in which regions and seasons (Kharif vs Rabi)
- Built regression models to predict yield based on rainfall, soil type, temperature, and historical trends
- Compared multiple approaches to find what works for this kind of agricultural data
- Visualized state-wise production patterns and identified underperforming regions with improvement potential

The notebook is meant to be readable - I added explanations at each step so someone without a data science background can follow the logic.

### 2. The web app (Vite + TypeScript)

A frontend built to make the insights accessible to non-technical users:

- **Crop recommendations** - enter your location, soil type, and season → get ranked suggestions for what to plant
- **Yield predictions** - estimate expected output based on historical data for your region
- **Weather integration** - pulls current and forecast weather data to factor into recommendations
- **Government schemes** - links to relevant agricultural subsidies and programs
- **Multi-language support** - because most farmers don't read English

The idea is that an agricultural extension worker or a farmer's son with a smartphone could open this and get useful information without needing to understand the ML behind it.

## Tech

| Component | Stack |
|:----------|:------|
| ML/Analysis | Python, Pandas, NumPy, Scikit-learn, Matplotlib, Seaborn |
| Frontend | Vite, TypeScript, React |
| Data | Indian agricultural datasets (crop production, weather, soil) |

## Running it

```bash
# Frontend
npm install
npm run dev

# ML notebook
jupyter notebook Agriculture.ipynb
```

## Limitations I'm honest about

- The models are trained on aggregated state-level data, not farm-level. Accuracy drops for micro-predictions.
- Weather forecasts beyond 5 days aren't reliable enough for planting decisions.
- The dataset doesn't include irrigation data, which is a huge factor in actual yields.
- No real user testing with farmers yet - this is still a prototype.

## What I'd do with more time

- Add satellite imagery analysis (NDVI) for real-time crop health monitoring
- Integrate with India's eNAM platform for market price data
- Build an offline-first mobile version (most rural India has spotty internet)
- Partner with an agricultural university for ground-truth validation
