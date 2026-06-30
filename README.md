# SemiSupply360 — Semiconductor Supply Chain Analytics Dashboard

A Power BI dashboard analyzing supplier performance, delivery reliability, and order fulfillment across a simulated semiconductor supply chain — built on a proper star schema with advanced DAX, drill-through navigation, and Row Level Security.

## Overview

This project simulates a real-world semiconductor manufacturing supply chain (suppliers, plants, products, and 900+ purchase orders) to analyze:
- Supplier performance and reliability
- On-time delivery rates
- Lead time variance (delivery delays/early arrivals)
- Order volume trends across 2024–2025
- Regional supplier breakdowns

## Data Model

Built using a star schema with one fact table and four dimension tables:

- *Fact_Orders* — order-level grain (900 rows): order date, supplier, product, plant, quantities, expected vs actual delivery dates, status
- *Dim_Supplier* — supplier master data: region, country, tier, rating
- *Dim_Product* — product catalog: category, product line, unit of measure
- *Dim_Plant* — manufacturing plant details: location, region, plant type
- *Dim_Date* — standard calendar table for time intelligence

All relationships are single-direction, one-to-many, connecting each dimension to the fact table.

## Features

*DAX Measures*
- OnTime Delivery % — percentage of orders delivered on or before the expected date
- Avg Lead Time Variance — average delivery delay (in days) across all orders

*Visuals*
- Supplier comparison bar chart (quantity ordered by supplier)
- Order volume trend line (by year)
- Supplier scorecard table with conditional formatting (color-coded on-time % and lead time variance)
- KPI cards for on-time delivery % and average lead time variance

*Advanced Functionality*
- *Drill-through*: click any supplier in the scorecard to navigate to a detail page showing their full order history
- *Row Level Security (RLS)*: a "Region Manager" role restricts visibility to APAC-region suppliers only, demonstrating data access control

## Tools & Skills Used

Power BI Desktop, Power Query (data shaping, header promotion), DAX (CALCULATE, DIVIDE, AVERAGEX, DATEDIFF), star schema modeling, conditional formatting, drill-through pages, Row Level Security.

## Files

- SemiSupply360.pbix — main Power BI file
- Fact_Orders.csv, Dim_Supplier.csv, Dim_Product.csv, Dim_Plant.csv — source data
