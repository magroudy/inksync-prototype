# Example Queries and Responses

This document provides sample user queries and expected response types to guide implementation and testing.

## Basic Queries

### Query 1: "How are beverage sales performing this year?"
**Expected Analysis:**
- Calculate YTD sales for beverages category
- Compare to same period last year
- Compare to YTD target
- Breakdown by SKU and region

### Query 2: "Which region is performing best in detergents?"
**Expected Analysis:**
- Rank regions by detergent category sales (value)
- Show percentage of target achieved
- Show growth vs last year
- Identify best performing SKUs in top region

### Query 3: "Are we on track to meet our annual targets?"
**Expected Analysis:**
- Calculate YTD performance vs YTD target (all categories)
- Project year-end based on current trend
- Identify categories/regions at risk of missing targets
- Highlight overperforming areas

## Intermediate Queries

### Query 4: "How has the price of cola_500ml changed over the last year?"
**Expected Analysis:**
- Calculate monthly price (value/volume) for cola_500ml
- Show price trend chart (text-based)
- Compare with price changes in other beverage SKUs
- Analyze impact of price changes on volume

### Query 5: "Which category shows the strongest quarterly growth?"
**Expected Analysis:**
- Calculate quarter-over-quarter growth for all categories
- Rank by growth percentage
- Show consistency of growth (volatility)
- Identify contributing factors (volume vs price)

### Query 6: "Compare performance in Cairo vs Alexandria this quarter"
**Expected Analysis:**
- Direct comparison of total sales (value & volume)
- Category-by-category breakdown
- Growth rates comparison
- Target achievement comparison

## Advanced Queries

### Query 7: "What's our best performing SKU in terms of value vs target?"
**Expected Analysis:**
- Rank all SKUs by percentage of target achieved
- Show consistency across regions
- Analyze growth trajectory
- Identify factors driving success

### Query 8: "Are there seasonal patterns in snack sales?"
**Expected Analysis:**
- Monthly analysis across multiple years
- Identify recurring patterns
- Compare seasonal patterns across regions
- Suggest inventory planning implications

### Query 9: "Which products have the highest price elasticity?"
**Expected Analysis:**
- Identify SKUs where volume changes correlate with price changes
- Calculate approximate elasticity coefficients
- Compare elasticity across categories
- Suggest pricing strategy implications

## Follow-up Question Examples

Each analysis should suggest 2-3 relevant follow-up questions, such as:

- "Would you like to see how this compares to the previous quarter?"
- "Should we analyze which SKUs are driving the growth in this category?"
- "Would you like to see a breakdown by price point?"
- "Shall I analyze the impact of regional promotions on these results?"
- "Would you like to see which targets are at highest risk of not being met?" 