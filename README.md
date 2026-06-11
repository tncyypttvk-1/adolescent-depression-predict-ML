# Adolescent Depression ML Project

**IKT446 — Machine Learning with R**  
Istanbul Medeniyet University

---

## 🎯 Project Overview

This research investigates the effectiveness of socio-economic and digital indicators in explaining adolescent depression prevalence across countries. Using data from 139 countries (2000-2022), we employed machine learning techniques to identify which factors (internet penetration, GDP per capita, urbanization) best predict depression rates.

## 📊 Key Findings

| Metric | Result |
|--------|--------|
| **Optimal Algorithm** | Random Forest |
| **CV RMSE** | 0.1880 |
| **Test RMSE** | 0.1923 |
| **R² (Variance Explained)** | 78.41% |
| **Most Important Feature** | GDP per Capita (42.3%) |

### Feature Importance

1. 💰 **GDP per Capita** (42.3%) - Reflects advanced diagnostic capacity
2. 🌐 **Internet Penetration** (31.7%) - Digital connectivity indicator
3. 🏙️ **Urbanization** (22.1%) - Urban density factor

## 📁 Project Structure

```
adolescent-depression-ml/
├── index.html                              # 🌐 Interactive landing page (EN/TR)
├── adolescent_depression_presentation_1.qmd # Quarto presentation source
├── adolescent_depression_ml_2.pptx         # PowerPoint presentation
└── README.md                               # This file
```

## 🚀 Getting Started

### View the Project Online
1. Open **`index.html`** in your web browser
2. Switch between **English (EN)** and **Turkish (TR)** using the toggle button
3. Explore the interactive project summary and file links

### Access Presentations
- **Quarto Presentation**: Interactive reveal.js slideshow with live R visualizations
- **PowerPoint Presentation**: Download and present with 15 professional slides

## 📋 Data & Methodology

### Data Sources
- **World Bank WDI**: Economic and urbanization indicators
- **IHME GBD 2019**: Global disease burden and health data
- **Time Range**: 2000-2022 (23 years)
- **Geographic Coverage**: 139 countries
- **Total Observations**: ~3,000 data points

### Methodology
- **Data Split**: 75% training, 25% testing
- **Cross-Validation**: 5-Fold CV
- **Algorithms Tested**:
  - Linear Regression (Baseline)
  - Decision Tree (CART)
  - Random Forest (Selected)
- **Hyperparameter Optimization**: Grid search over mtry [1-4] and min_n [2-20]

### Data Pipeline
```
Raw Data
  ↓
[step_impute_median] → Handle missing values
[step_log(gdp_pc)] → Compress right-skewed economic data
[step_normalize] → Standardize features (μ=0, σ=1)
[step_zv] → Remove zero-variance variables
  ↓
Model Training & Cross-Validation
  ↓
Optimal Parameters: mtry=2, min_n=5
```

## 🛠️ Technology Stack

| Technology | Purpose |
|-----------|---------|
| **R** | Core statistical analysis and modeling |
| **tidymodels** | ML workflow, recipe engineering, and hyperparameter tuning |
| **ggplot2** | Data visualization with cyberpunk aesthetic |
| **corrplot** | Correlation matrix visualization |
| **Quarto** | Dynamic document and presentation rendering |
| **Reveal.js** | Interactive web-based presentation framework |

## 🔬 Research Question

**Do countries' internet penetration rates, per-capita GDP levels, and urbanisation rates significantly explain adolescent depression prevalence (%)?**

### Hypotheses
- **H1**: Higher GDP per capita → Better diagnostic tracking (positive correlation)
- **H2**: Higher internet penetration → More depression reports (positive correlation)
- **H3**: Higher urbanization → More depression indicators (positive correlation)

## 📈 Key Results

### Model Performance
```
Algorithm                  | CV RMSE | SE      | Test RMSE
--------------------------|---------|---------|----------
Random Forest (Selected)   | 0.1880  | 0.0021  | 0.1923 ✓
Decision Tree              | 0.2134  | 0.0038  | —
Linear Regression          | 0.2297  | 0.0044  | —
```

### Feature Correlations
```
internet_pen ↔ urbanization:    r = 0.63
internet_pen ↔ gdp_pc:          r = 0.67
urbanization ↔ gdp_pc:          r = 0.57
dep_pct ↔ internet_pen:         r = 0.31
```

High multicollinearity (r > 0.57) justified the use of Random Forest ensemble methods.

## 📚 Deliverables

1. **Interactive Index Page** (`index.html`)
   - Bilingual interface (English/Turkish)
   - Project summary and statistics
   - Links to all presentation materials
   - Responsive design (mobile/desktop)

2. **Quarto Presentation** (`adolescent_depression_presentation_1.qmd`)
   - Reveal.js framework
   - Dynamic R code execution
   - Live visualizations
   - Dark theme with cyberpunk aesthetics

3. **PowerPoint Presentation** (`adolescent_depression_ml_2.pptx`)
   - 15 detailed slides
   - EDA visualizations
   - Model performance metrics
   - Feature importance charts
   - Residual diagnostics

## ⚠️ Important Notes

**Non-Causal Relationships**: This analysis identifies statistical associations, not causal relationships. The observed correlations likely reflect:
- Advanced diagnostic infrastructure in developed nations
- Better healthcare reporting systems
- Enhanced digital connectivity enabling health monitoring

Depression prevalence is not *caused* by internet penetration or GDP; rather, these factors correlate with more comprehensive reporting and diagnosis infrastructure.

## 🔗 Links

- **Student**: Tuncay Yaptitevek
- **University**: Istanbul Medeniyet University
- **Course**: IKT446 — Machine Learning with R
- **Date**: May 18, 2026
- **Email**: tuncay.yaptitvek@std.medeniyet.edu.tr

## 📄 License

© 2026 Tuncay Yaptitevek. All rights reserved.

---

### How to Use This Repository

```bash
# Clone the repository
git clone https://github.com/yourusername/adolescent-depression-ml.git
cd adolescent-depression-ml

# Open the landing page
open index.html  # macOS
start index.html # Windows
xdg-open index.html # Linux

# Or use a local server
python -m http.server 8000
# Then visit http://localhost:8000
```

### Language Selection
The index page remembers your language preference using browser localStorage.
- **Click EN** for English
- **Click TR** for Turkish (Türkçe)

---

## 🎨 Design Features

- **Dark Cyberpunk Theme**: Professional aesthetic with neon accents
- **Color Palette**:
  - Cyan (#00F5D4) - Primary accent
  - Pink (#FF007F) - Secondary highlight
  - Green (#39FF14) - Success/positive
  - Orange (#FF9F1C) - Important metrics
- **Responsive**: Optimized for mobile, tablet, and desktop
- **Accessible**: Clear typography and high contrast ratios

---

*Last Updated: June 2026*
