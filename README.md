# Global Analysis of Coffee Affordability

## Project overview

This project analyses coffee affordability across cities worldwide with a student-centred focus.  
We ask four related questions: 
    (1) How much of a typical resident’s daily income does one cup of coffee consume? (income-based affordability), 
    (2) Is coffee cheap or expensive relative to the local price environment (price-context), 
    (3) For a fixed student coffee budget, how many days will one cup per day last (Coffee Survival Index), and
    (4) What are the most stategic locations for coffee-loving students based on coffee affordability, relative coffee prices, and general price levels?

To answer these questions we combine cleaned city-level price data (coffee, restaurant and market items) with average monthly net salaries. The analysis constructs a simple city–price index, several affordability metrics, and a compact “student score” to rank cities for caffeine-addicted students. The notebook `analysis.ipynb` reproduces all steps and exports the main tables and figures in the `figures/` folder.

## Analysis

The analysis proceeds in several structured steps, each adding a different perspective on coffee affordability.

First, city-level coffee prices are combined with average monthly net salaries to compute an **income-based coffee affordability metric**, defined as the share of a typical daily income required to purchase one cup of coffee. This measure captures the direct burden of coffee consumption relative to local earnings and allows meaningful comparison across cities with very different income levels.

Second, to account for broader cost-of-living conditions, we construct a **general city price index** using available price information beyond coffee. The index is defined as the average of restaurant and market price levels for each city. Coffee prices are then normalized by this index to obtain a **relative coffee price**, indicating whether coffee is cheap or expensive compared to other everyday goods and services in the same city.

Third, a student-oriented **Coffee Survival Index** is introduced. For a fixed monthly coffee budget (baseline: 30 USD), the index measures how many days a student can afford one cup of coffee per day in a given city. This metric is intuitive and complements the income-based measure by focusing on absolute prices rather than income shares.

Finally, these dimensions are combined into a simple **student score** that integrates coffee affordability, relative coffee prices, and general price levels. This composite indicator is used to rank cities in terms of overall coffee friendliness for students. Throughout the analysis, results are visualized using scatter plots, bar charts, and country-level aggregations to highlight relationships between income, prices, and affordability.

## Key findings

- **Income is the dominant driver of coffee affordability.**  
  Cities with higher average incomes consistently exhibit lower coffee affordability burdens, even when absolute coffee prices are relatively high (viz. "income_vs_coffee.png"). Furthermore, coffee affordability is driven much more by income differences than by general price levels (markets or restaurants). Cities with high restaurant or market prices often maintain low coffee affordability burdens due to higher income levels. In contrast, cities with lower restaurant or market prices can still experience poor coffee affordability when income levels are low. (viz. "market_vs_coffee.png" and "restaurant_vs_coffee.png" plots)

- **Coffee prices normalized by local price levels provide important context.**  
  After controlling for the general price environment using a city-level price index, coffee that appears cheap in absolute terms can still be relatively expensive in low-income cities. (viz. "relative_price_vs_affordability.png" plot)

- **Student budget outcomes depend primarily on absolute coffee prices.**  
  Because the Survival Index is calculated as a fixed budget divided by the absolute coffee price, rankings by survival largely reflect differences in absolute coffee prices. The index is therefore complementary to the income-based affordability metric, which captures relative burden rather than absolute cost. Top 10 cities with lowest coffee prices in absolute terms are displayed by the horizontal bar chart "top_10_cities_by_survival.png". Overall, survival days tend to be lower in high-income cities where coffee prices are higher. (viz. "survival_vs_income.png" plot)

- **A small set of cities consistently performs well across multiple dimensions.**  
  When affordability, relative prices, and general price levels are combined into a composite student score, the top-ranked cities offer a favorable balance between income, local prices, and everyday consumption costs, making them particularly attractive for coffee-consuming students.

## Data
The analysis relies on city-level cost-of-living collected from RapidAPI, specifically the Cost of Living and Prices API and and income data collected from Numbeo. 
City-level prices are collected for items in two categories: restaurants and markets. Coffee prices are measured using the cappuccino item, which serves as a consistent proxy for out-of-home coffee consumption. For each item, the API reports minimum, average, and maximum prices in local currency and in USD. The analysis uses average prices in USD to ensure comparability across cities.


## Limitations
- Snapshot data only (no timeseries); results reflect the dates the datasets were collected.
- No city-level geocoding of coffee affordability was performed (we used country-level aggregation for spatial views).
- The price index uses a simple mean of restaurant and market averages — alternative weightings are possible.


## How to run the project
1. Clone the repository:
   ```bash
   git clone https://github.com/luckakovy/Global-Analysis-of-Coffee-Affordability-Best-Cities-for-Boke-Caffeine-Addicted-Students.git

  Alternatively, download the repository as a ZIP file from GitHub and extract it.

2. Install the required Python packages:
   ```bash
   pip install -r requirements.txt

3. Open the project in Jupyter Notebook or VS Code.

4. Run the final notebook:
   - Open `main.ipynb`
   - Restart the kernel
   - Run all cells from top to bottom

   This notebook presents the final results of the project.

5. (Optional) Explore the full analysis:
   - `analysis.ipynb` contains the exploratory analysis, intermediate steps, and robustness checks.
   - It is used to generate the outputs displayed in `main.ipynb`.

