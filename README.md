# Global Analysis of Coffee Affordability

## Project overview

This project analyses coffee affordability across cities worldwide with a student-centred focus.  
We ask three related questions: 
    (1) How much of a typical resident’s daily income does one cup of coffee consume? (income-based affordability), 
    (2) Is coffee cheap or expensive relative to the local price environment (price-context), and 
    (3) For a fixed student coffee budget, how many days will one cup per day last (Coffee Survival Index)?

To answer these questions we combine cleaned city-level price data (coffee, restaurant and market items) with average monthly net salaries. The analysis constructs a simple city–price index, several affordability metrics, and a compact “student score” to rank cities for caffeine-addicted students. Data cleaning and initial extraction were performed by the team (see Data section). The notebook `analysis.ipynb` reproduces all steps and exports the main tables and figures in the `figures/` folder.

## Analysis

The analysis proceeds in several structured steps, each adding a different perspective on coffee affordability.

First, city-level coffee prices are combined with average monthly net salaries to compute an **income-based coffee affordability metric**, defined as the share of a typical daily income required to purchase one cup of coffee. This measure captures the direct burden of coffee consumption relative to local earnings and allows meaningful comparison across cities with very different income levels.

Second, to account for broader cost-of-living conditions, we construct a **general city price index** using available price information beyond coffee. The index is defined as the average of restaurant and market price levels for each city. Coffee prices are then normalized by this index to obtain a **relative coffee price**, indicating whether coffee is cheap or expensive compared to other everyday goods and services in the same city.

Third, a student-oriented **Coffee Survival Index** is introduced. For a fixed monthly coffee budget (baseline: 30 USD), the index measures how many days a student can afford one cup of coffee per day in a given city. This metric is intuitive and complements the income-based measure by focusing on absolute prices rather than income shares.

Finally, these dimensions are combined into a simple **student score** that integrates coffee affordability, relative coffee prices, and general price levels. This composite indicator is used to rank cities in terms of overall coffee friendliness for students. Throughout the analysis, results are visualized using scatter plots, bar charts, and country-level aggregations to highlight relationships between income, prices, and affordability.

## Key findings

- **Income is the dominant driver of coffee affordability.**  
  Cities with higher average incomes consistently exhibit lower coffee affordability burdens, even when absolute coffee prices are relatively high (viz. "income_vs_coffee.png" plot). Furthermore, coffee affordability is driven much more by income differences than by general price levels (markets or restaurents). Cities with high restaurant or market prices often maintain low coffee affordability burdens due to higher income levels. In contrast, cities with lower restaurant or market prices can still experience poor coffee affordability when income levels are low. (viz. "market_vs_coffee.png" and "restaurant_vs_coffee.png" plots)

- **Coffee prices normalized by local price levels provide important context.**  
  After controlling for the general price environment using a city-level price index, coffee that appears cheap in absolute terms can still be relatively expensive in low-income cities. (viz. "relative_price_vs_affordabilit" plot)

- **Student budget outcomes depend primarily on absolute coffee prices.**  
  The Coffee Survival Index shows that a fixed monthly coffee budget lasts longer in cities with lower absolute coffee prices, regardless of income levels (intuitively) - order of cities by survival index exactly corresponds to order of cities based on the coffee prices in USD - top 10 cities with lowest coffee prices in absolute terms: "top_10_cities_by_survival.png". As a result, survival days tend to be lower in high-income cities where coffee prices are higher. (viz. "survival_vs_income.png" plot)

- **A small set of cities consistently performs well across multiple dimensions.**  
  When affordability, relative prices, and general price levels are combined into a composite student score, the top-ranked cities offer a favorable balance between income, local prices, and everyday consumption costs, making them particularly attractive for coffee-consuming students.
