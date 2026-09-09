# Zomato-end-to-end-analytics

An interactive Power BI dashboard analyzing Zomato's global restaurant data — covering ratings, cuisines, pricing, delivery availability, and geographic spread across 15 countries.

## Overview

This project explores a dataset of 9,542 restaurants listed on Zomato to uncover patterns in customer ratings, pricing, cuisine popularity, and service availability (online delivery and table booking) across different countries and localities.

## Key Metrics

- **Total Restaurants:** 9,542
- **Countries Covered:** 15
- **Average Rating:** 3.44 / 5.0 (filtered to rated restaurants only)
- **Online Delivery Availability:** 25.7%
- **Table Booking Availability:** ~12%

## Dashboard Sections

1. **KPI Overview** — Total restaurants, average rating, countries, average cost for two, and online delivery percentage.
2. **Online Delivery Share** — Donut chart showing the split between delivery-enabled and non-delivery restaurants.
3. **Table Booking Share** — Gauge chart showing what proportion of restaurants offer table booking.
4. **Geographic Reach** — Map visualizing restaurant distribution across countries.
5. **Top Popular Cuisines** — Bar chart ranking the most common cuisines.
6. **Lowest Rated Localities** — Table highlighting localities that need improvement.
7. **Price Range Distribution** — Bar chart showing restaurant counts across four price tiers.
8. **Rating vs Votes Dispersion** — Scatter plot exploring the relationship between restaurant popularity (votes) and average rating.

## Tools Used

- **Power BI Desktop** — data modeling, DAX measures, and visualization
- **Power Query** — data cleaning and transformation

## Key DAX Measures

```DAX
Average Rating = 
CALCULATE(
    AVERAGE('zomato_cleaned'[Aggregate rating]),
    'zomato_cleaned'[Is Rated] = TRUE()
)

Table Booking Count = 
CALCULATE(
    COUNTROWS('zomato_cleaned'),
    'zomato_cleaned'[Has Table booking] = "Yes"
)
```

## Dataset

The dataset (`zomato_cleaned.csv`) includes restaurant-level details: name, country, city, locality, cuisines, cost for two, ratings, votes, and service availability flags.

**Note:** Average cost figures are reported in each restaurant's local currency and are not converted to a common currency. Aggregate cost KPIs in this dashboard are based on India (INR) data only, since it represents the majority of the dataset.

## How to View

1. Download `zomato_dashboard.pbix`
2. Open with [Power BI Desktop](https://www.microsoft.com/en-us/power-platform/products/power-bi/downloads) (free)

## Repository Structure

```
zomato-global-operations-dashboard/
├── zomato_dashboard.pbix
├── zomato_cleaned.csv
└── README.md
```
