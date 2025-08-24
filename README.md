# Airline Safety Analysis (1985–2014)

## Project Overview
This project analyzes airline safety data to compare changes in fatality rates across different airlines over two periods: 1985–1999 and 2000–2014. It highlights which airlines improved or got worse, and includes a simple model to predict risk.

## Dataset
- **Source**: FiveThirtyEight’s “airline-safety.csv” dataset.
- **Contents**: Safety records (incidents, fatal accidents, fatalities) and seat-kilometers for ~50 airlines.
- **Direct link to raw CSV**: [airline-safety.csv](https://raw.githubusercontent.com/fivethirtyeight/data/master/airline-safety/airline-safety.csv)

## Steps & Methodology

1. **Data Loading & Cleaning**  
   - Renamed columns for clarity.  
   - Ensured correct numeric types.  

2. **Feature Engineering**  
   - Scaled seat-km to billions for readability.  
   - Calculated incident and fatality **rates per billion seat-km** for each period.  
   - Calculated **changes** between the two periods.  
   - Created a binary variable: `had_fatal_0014` to indicate if an airline had any fatal accidents in 2000–2014.

3. **Exploratory Data Analysis (EDA)**  
   - **Top 10 airlines by fatality rate** (2000–2014): Visualized those with highest fatalities per billion seat-km.  
   - **Change in fatality rates**: Visualized improvements (negative change) and worsening (positive change) trends between the two periods.
     
4. **Simple Risk Modeling** :
   - Used logistic regression to predict `had_fatal_0014` based on previous safety rates and size.  
   - Evaluated using classification report and ROC curve (AUC ≈ 0.64): moderate separation, indicative given small dataset.

5. **Model Evaluation** :
   - Visualized the **ROC Curve** to show model discrimination ability.

## Key Insights :
- Some airlines showed **dramatic improvement** in fatality rates, while others worsened.
- Model performance (ROC-AUC ≈ 0.64) indicates limited predictive power, likely due to small sample size—but still provides a simple risk signal worth exploring.

## Visual Highlights :
- **Top 10 Fatalities per Billion seat-km (2000–14)**: Identifies airlines with highest safety risk based on rate.  
- **Change in Fatality Rate**: Shows which airlines decreased or increased in risk over time.  
- **ROC Curve**: Illustrates model’s ability to predict fatal accidents in the second period.

## Future Improvements (Optional) :
Add airline type (e.g. government vs private) to see if it predicts risk.
Use clustering to group airlines by risk profiles.
Expand model features or try tree-based models.

Add interactivity or a web dashboard (e.g. with Plotly or Streamlit).

