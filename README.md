# Operational-And-Financial-Analysis-of-Furniture-Retail-Performance

<div align="center">
  <img src="https://github.com/David-TheAnalyst/Operational-And-Financial-Analysis-of-Furniture-Retail-Performance/blob/main/2.%20Furniture%20Sales%20DB.png" alt="Flowpal Sales Dashboard Additional View" width="1000" height="600">
</div>

## **Introduction**

This study aims to quantify the drivers behind declining profitability, isolate inefficiencies within the order-to-delivery value chain, and surface category-level, geographic, and operational levers that can be optimized. Ultimately, the goal is to deliver a data-driven roadmap that supports margin recovery, operational discipline, and sustainable revenue growth.

Despite healthy commercial traction reflected in rising sales revenue ($742.0K) and growing order volume (8.0K units), the business is experiencing a severe erosion in profitability, with YoY profit collapsing to $18.5K (–57% YoY). This widening gap signals a structural breakdown in pricing, cost-to-serve, or both.

This calls for a core analytical questions:

- Which product categories are silently driving losses despite high volume.
-	Which geographies or metropolitan hubs generate revenue but destroy margin due to high operating or logistics costs.
-	How shipping modes and delivery durations contribute to inflated fulfillment expenses.
-	Whether pricing strategy, promotional activity, or customer mix is diluting gross margin.

By diagnosing these issues empirically, this project provides clear, actionable interventions that leadership can implement immediately ranging from pricing recalibration and category-level optimization to improved logistics planning and region-specific strategies.
This analysis is not merely a performance review; it is an operational mandate to halt margin deterioration and reposition the business for profitable, defensible, and scalable growth.


## **Key Datasets and Methodologies:**

The project uses a single, comprehensive dataset for over 2100 furniture sales transaction that contains the following column. 
The Methodologies employed in Microsoft Excel include

-	Data consolidation via Power Query (where I carried out all the data cleaning procedure)
-	Pivot Tables (multi-level aggregation by region, city, category)
-	Calculated columns (YoY growth)
-	Slicers and Timeline controls for interactive dashboards
-	Dynamic Slicers (Using Excel function like INDEX/MATCH, and MAX)

## **Story of Data:**

The sourced data from a furniture company website that houses the complete record of all the 2122 transactions executed over the years. 
It is structured list of individual sales transactions, with 22 columns including: order id, date, city, state, region, product category, product subcategory, quantity, sales amount, cost, shipping cost, shipping mode, shipping_duration_days)

## **Data Splitting and Preprocessing:**

Whilst cleaning the data I ensured there were no blank rows and duplicate values. I then used Power Query to do most of the cleaning and Standardization which include

Ensuring the Order date was in the right format.

While transforming the column, I appended some new columns:

-	Month column added (TEXT(order_date,"mmm") / MONTH order).
-	YoY% computed by grouping by month and comparing to prior year where applicable.
-	Shipping Duration Buckets created (0,1,2,3,4,5,6,7+ days).
-	Appending New Column like: Delivery duration, Year, Month name, Profit Margin, Heavily Discounted Orders.


## **Pre-Analysis:**

Data Split: 

-	Dependent variable(s): Profit (gross), Profit margin %, Sales.
-	Independent variables: product_category, region, state, city, shipping_mode, shipping_duration, month, duration

Industry Context: Furniture & Home Furnishings Retail Industry.

Stakeholders:

-	Executive leadership (CEO/CFO/COO)
-	Sales & Marketing leadership, 
- Inventory managers, Regional Ops & Logistics.

Value to the Industry:
- The analysis identifies margin leakage sources, optimizes price & shipping policies, reduces delivery costs via regional fulfillment, and aligns marketing spend to profitable categories and cities. The Implemented recommendations would directly improve gross margin and operational scalability.


## **In-Analysis:**

Key Observation: 

1. Top-level metrics: Sales = $742.0K (+6% YoY), Quantity = 8.0K (+11% YoY), Profit = $18.5K (−57% YoY).
 
2. Category concentration: Chairs = $328.4K (~44% of sales).
 
3. Shipping: Standard Class = 59% of orders.
 
4. Shipping duration: Peak at 4 days = 28%, long tail up to 7+ days.
 
5. Geography: Top revenue cities: NYC ($75.7K), LA ($54.0K), Seattle ($41.0K), Philadelphia ($38.5K), San Francisco ($36.4K).
 
5. 	High-volume categories (Chairs) correlate with high shipping costs (weight/size), correlating to margin pressure.

7. 	Standard Class usage correlates with longer delivery durations and potentially higher damage/return rates (not modeled here but operationally plausible).

8. 	Metro deliveries (NYC) correlate with higher operational overhead (last-mile costs).

**Initial Insights:**

Based on the observation, the Unit growth being faster than revenue growth, indicate an ASP compression (price cuts, lower-priced mix).
The severe Profit decline suggests unprofitable promotional strategy or rising per-order fulfillment cost not passed to customers.

**Preliminary Recommendations from In-Analysis:**

-	Suspend or restrict deep discounts for high-shipping SKUs until SKU-level margin is audited.
-	Reprice shipping for Standard Class (or add fuel/handling surcharge) to reflect real cost.
-	Pilot regional cross-dock or micro-fulfillment hub in high-volume east/west clusters to reduce last-mile cost/duration.
-	Introduce dynamic shipping rules: auto-upgrade or redirect high-cost metro orders to fastest profitable fulfillment method or apply explicit surcharge.


## **Post-Analysis and Insights**

Key Findings:

-	Growth without margin: Sales +6% and Quantity +11% accompanied by Profit −57% is a clear evidence of margin erosion due to price decreases and/or cost increases.
-	Category concentration risk: Chairs represent $328.4K (44% of revenue) but are likely the largest absolute loss contributor given high shipping and promotional exposure.
-	Shipping economics broken: Standard Class at 59% is dominant and correlated with multi-day delivery that increases operational cost and returns.
-	Geographic imbalance: East region heavily dependent on NYC ($75.7K); West region more diversified (LA, Seattle, SF) and currently more profitable.
-	Fulfillment inconsistency: Delivery durations are inconsistent (4-day mode is 28% but many 5–7+ day deliveries), indicating uneven service levels and capacity constraints.

Comparison with Initial Findings

-	The initial dashboard signals were validated: the business is growing units but losing margin; Chair dependence and Standard Class dominance are primary operational risk drivers. 


## **Data Visualizations & Charts:**

 <div align="center">
  <img src="https://github.com/David-TheAnalyst/Operational-And-Financial-Analysis-of-Furniture-Retail-Performance/blob/main/2.%20Furniture%20Sales%20DB.png" alt="Flowpal Sales Dashboard Additional View" width="800" height="500">
</div>

Above is a single-page dynamic dashboard created in Excel that can be sliced by the 4 different Regions.

Key Metrics Displayed: 

-	Sales (SUM) with YoY Growth: $742.0k, +8% YoY 
-	Quantity with YoY Growth: 8.0k, +11% YoY
-	Profit with YoY Growth: $18.5k, -57% YoY

**Charts & Visuals to Include in Excel Dashboard**

Line Chart: 

- Monthly Sales Trend: Seasonality spike Nov–Dec (peak month Dec ~$121.8K).

Donut/ Ring Chart 

-	Shipping Mode: Standard Class dominates (59%) — immediate operational lever.

Dot/Line Chart by Days

- Shipping Duration: 4-day delivery is most common (28%); 5-day (22%); 6+ days notable (11%+6% etc.), indicating long tail.

Filled Map

- Sales by State: West and East coastal states show higher intensity; target states for fulfillment hubs identified.

Horizontal Bars Chart

-	Top 5 Best-Selling Cities: NYC ($75.7K) highest; shows geographic concentration risk.
- Category Breakdown: Chairs lead at $328.4K, followed by Tables ($207.0K), Bookcases ($114.9K), Furnishings ($91.7K).


## **Recommendations and Observations:**

**Specific Recommendations:**

1.	Price & Promotion Control
-	Immediately pause deep discounts on Chairs and run an SKU-level margin audit. Reinstitute promotions only where Cost of Goods Sold + shipping + overhead < promotional price.
-	Implement minimum advertised price rules for high-shipping SKUs.

2.	Shipping Economics & Pricing
-	Reprice Standard Class: introduce a shipping surcharge for bulky/heavy SKUs or zonal surcharges for metro deliveries to reflect actual cost.
- Offer guaranteed 4-day delivery as a priced option; free shipping only when margin is preserved.

3.	Operational Changes
-	Pilot a micro-fulfillment hub in the Northeast (to serve NYC/Philadelphia) and in the West (to serve LA/Seattle/SF) to reduce last-mile costs and delivery duration.
-	Rebalance inventory to regional nodes during Oct–Dec to reduce lead time and shipping cost.

4.	Category & Product Strategy
-	Diversify revenue mix by upselling Furnishings and Bookcases (higher margin, lighter/cheaper to ship) with bundled offers.
-	Re-evaluate SKU assortment for Chairs — consider premiumization (higher ASP) for certain SKUs to recover margin.

5.	Operational KPIs & Monitoring
-	Add KPIs to dashboard: COGS %, Shipping Cost per Order, Margin per Order, Returns rate by SKU, and Fulfillment Cost by Zone.
-	Add alerts for any city/zip where margin < target threshold.

6.	Regional Marketing & Pricing
-	East: replicate West’s disciplined price strategy; diversify marketing spend to other East cities to reduce NYC concentration risk.
-	West: continue promotional execution timing for December peak; emphasize high-margin Tables.

**Optimizations / Business Decisions**

- Short-term: tighten promotions and adjust shipping pricing.
-	Mid-term: invest in one or two micro-fulfillment hubs (ROI within 6–12 months with shipping savings).
-	Long-term: revise SKU portfolio to favor higher-margin, lower-shipping-cost products.

Unexpected Outcomes & Explanations

-	Observation: Quantity grew faster than Sales — implies lower ASP, possibly due to discounts or shift to lower-priced SKUs.
-	Explanation: Likely intentional discounting to acquire share or reduce inventory; but not sustainable without shipping-cost adjustments.


## **Conclusion:**

The business demonstrates demand and volume growth, but the margin collapse (−57% YoY) indicates critical misalignment between pricing, shipping economics, and promotional strategy. Chairs drive top-line but are likely the primary drivers of margin leakage due to size/weight and promotional exposure. 

The Standard Class shipping usage (59% of total) and inconsistent delivery times (long tail to 7+ days) magnify cost and customer experience risks. Geo-concentration in NYC elevates business risk and the West is more diversified and profitable.


## **Limitations:**

The primary limitation is that the per-order carrier invoice-level shipping costs and returns/refund feed were not available for per-order reconciliation and shipping cost allocations are estimated or allocated.

## **References:**

1.	Customer lifetime value (LTV) analysis vs. CAC to determine acceptable promotional elasticity.
2.	Returns and damages analysis to quantify bottom-line impact of shipping speed/mode.

12. References & Appendices
References
•	Furniture Sales Dataset (Source)
•	Microsoft Excel (Analytical Tool): Pivot Tables, Power Query, INDEX/MATCH functions.

<h3 align="left">Connect with me on Socials:</h3>
<p align="left">
<a href="https://linkedin.com/in/david-ojo-984557231/" target="blank"><img align="center" src="https://raw.githubusercontent.com/rahuldkjain/github-profile-readme-generator/master/src/images/icons/Social/linked-in-alt.svg" alt="david ojo" height="30" width="40" /></a>
<a href="https://twitter.com/david_ojo_1" target="blank"><img align="center" src="https://raw.githubusercontent.com/rahuldkjain/github-profile-readme-generator/master/src/images/icons/Social/twitter.svg" alt="david_ojo_1" height="30" width="40" /></a>
<a href="https://medium.com/@davidojo2214" target="blank"><img align="center" src="https://raw.githubusercontent.com/rahuldkjain/github-profile-readme-generator/master/src/images/icons/Social/medium.svg" alt="@davidojo" height="30" width="40" /></a>
<a href="http://www.youtube.com/@DavidOjo-j3v" target="blank"><img align="center" src="https://raw.githubusercontent.com/rahuldkjain/github-profile-readme-generator/master/src/images/icons/Social/youtube.svg" alt="davidojo-j3v" height="30" width="40" /></a>
</p>


Thanks for stopping by!
