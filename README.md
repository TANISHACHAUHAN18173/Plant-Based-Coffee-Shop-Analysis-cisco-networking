# Plant-Based-Coffee-Shop-Analysis-cisco-networking

This project analyzes a survey dataset of coffee enthusiasts to identify the most popular dairy and plant-based alternatives. The goal is to provide insights for a new specialty coffee shop that plans to offer only plant-based beverages.

# 📁 Project Source

This project was offered as part of a Cisco Networking Academy data science activity.

# 📁 Dataset

The dataset used is coffee-survey-results.csv, containing survey responses from approximately 1,000 coffee drinkers, including:

Age range

Cups of coffee consumed per day

Dairy or plant-based additions

Type of dairy used

Sugar/sweetener preferences

Brewing methods

For this analysis, we focus on 8 dairy/plant-based options:

Whole milk

Skim milk

Half and half

Coffee creamer

Flavored creamer

Oat milk

Almond milk

Soy milk

# 🧪 Analysis Workflow
1. Import Libraries & Load Data
import pandas as pd
survey = pd.read_csv('coffee-survey-results.csv')
2. Extract Dairy Columns
needed_columns = [
    "What kind of dairy? (Whole milk)",
    "What kind of dairy? (Skim milk)",
    "What kind of dairy? (Half and half)",
    "What kind of dairy? (Coffee creamer)",
    "What kind of dairy? (Flavored creamer)",
    "What kind of dairy? (Oat milk)",
    "What kind of dairy? (Almond milk)",
    "What kind of dairy? (Soy milk)"
]
dairy = survey[needed_columns]
3. Clean & Rename Columns
name_map = {
    "What kind of dairy? (Whole milk)": "Whole milk",
    "What kind of dairy? (Skim milk)": "Skim milk",
    "What kind of dairy? (Half and half)": "Half and half",
    "What kind of dairy? (Coffee creamer)": "Coffee creamer",
    "What kind of dairy? (Flavored creamer)": "Flavored creamer",
    "What kind of dairy? (Oat milk)": "Oat milk",
    "What kind of dairy? (Almond milk)": "Almond milk",
    "What kind of dairy? (Soy milk)": "Soy milk"
}
dairy = dairy.rename(columns=name_map)
dairy = dairy.dropna()
4. Calculate Dairy Preferences
dairy_preferences = dairy.mean() * 100
dairy_preferences = dairy_preferences.sort_values()
dairy_preferences
5. Interactive Visualization with Plotly
import plotly.express as px


fig = px.bar(
    dairy_preferences,
    x=dairy_preferences.values,
    y=dairy_preferences.index,
    orientation='h',
    labels={'x': 'Percent', 'y': 'Dairy Type'},
    title="Interactive Dairy Preference Chart",
)
fig.show()
# 📊 Key Insights

Most popular dairy: Whole milk (56.2%)

Most popular plant-based milk: Oat milk (38.8%)

Many coffee enthusiasts use multiple dairy options, so percentages exceed 100% when summed.

Recommendation for a plant-based coffee shop:

Stock oat milk as the default plant-based option.

Consider offering almond milk and soy milk as secondary options for variety.







 <img src="<img width="883" height="309" alt="image" src="https://github.com/user-attachments/assets/aad54b2f-2043-4fef-8299-190aab0e32b7" />

