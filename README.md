# 🏠 Airbnb Global Listings Intelligence Dashboard — Tableau Business Analytics Project

<p align="center">
  <img src="https://img.shields.io/badge/Tool-Tableau%202024.1-blue?logo=tableau&logoColor=white" />
  <img src="https://img.shields.io/badge/Domain-Hospitality%20%7C%20Short--Term%20Rental-orange" />
  <img src="https://img.shields.io/badge/Type-Business%20Intelligence%20Dashboard-blueviolet" />
  <img src="https://img.shields.io/badge/Views-6%20Interactive%20Charts-brightgreen" />
  <img src="https://img.shields.io/badge/Data-Global%20Airbnb%20Listings-red" />
  <img src="https://img.shields.io/badge/Status-Published%20on%20Tableau%20Public-success" />
</p>

---

## 📌 Table of Contents

- [Business Problem](#-business-problem)
- [Project Objective](#-project-objective)
- [Dashboard Overview](#-dashboard-overview)
- [Dataset & Data Source](#-dataset--data-source)
- [KPIs & Metrics](#-kpis--metrics)
- [Dashboard Walkthrough](#-dashboard-walkthrough)
- [Key Insights](#-key-insights)
- [Business Recommendations](#-business-recommendations)
- [Tableau Features Used](#-tableau-features-used)
- [How to Use](#-how-to-use)
- [Project Structure](#-project-structure)
- [Author](#-author)

---

## 🧩 Business Problem

### Industry Challenge

The **global short-term rental market** — led by Airbnb's network of millions of listings across every inhabited continent — is one of the most data-intensive yet analytically under-served sectors in travel and hospitality. Hosts, property managers, investors, and platform strategists all face the same fundamental challenge: **navigating an overwhelming volume of listing data without a unified visual intelligence layer** that surfaces actionable pricing, availability, demand, and performance signals.

Without a BI dashboard, key strategic questions go unanswered:
- Which countries and geographies command the highest average nightly prices?
- Which property types and room configurations dominate supply?
- Which hosts are the most prolific operators — and at what average price?
- Where is calendar availability highest, signalling under-demand or over-supply?
- How do guest review volumes and satisfaction scores vary by geography and room type?
- Which individual properties offer the highest bedroom capacity with the best review scores?

### Why It Matters

| Stakeholder | Pain Point | Dashboard Value |
|---|---|---|
| **Property Investors** | No quick geographic comparison of pricing and availability | Instantly benchmark returns across countries with an interactive price map |
| **Existing Hosts** | No visibility into competitor pricing or host market share | Identify top host benchmarks and competitive price positioning |
| **Platform Analysts** | No consolidated view of supply, demand, and engagement | Monitor global supply concentration and review health from one screen |
| **Revenue Managers** | Cannot correlate price, availability, and review score simultaneously | Find the optimal balance between price competitiveness and guest satisfaction |
| **Hospitality Strategists** | No geographic intelligence on pricing corridors | Understand global pricing patterns through an interactive choropleth map |

### Business Impact

This dashboard directly enables:
- **Pricing strategy decisions** informed by country-level and property-type benchmarks
- **Market entry intelligence** — identifying under-served geographies with high availability and moderate prices
- **Host performance benchmarking** — comparing listing volumes and pricing across the top operators
- **Guest experience monitoring** — tracking review scores and volumes by country as a platform health KPI
- **Inventory composition analysis** — understanding which room types and property configurations dominate each market

---

## 🎯 Project Objective

This project delivers an **interactive, single-screen Tableau BI dashboard** that consolidates six analytical views into a unified, cross-filtered intelligence surface for global Airbnb listing analysis.

**Analytical Objectives:**
- Map pricing corridors across all listed countries using geographic visualisation
- Rank hosts by listing volume and correlate with their average pricing power
- Identify the most common property types and understand their room type composition
- Surface the highest-capacity properties ranked by total bedrooms, with review and stay policy context
- Compare availability patterns across countries to detect over-supplied and under-served markets
- Analyse review volume and satisfaction scores by country and room type

**Business Objectives:**
- Enable stakeholders to make pricing and investment decisions from a single, unified view
- Provide an interactive filter layer (price range, country, listing) that dynamically updates all views
- Surface top-10 performers across hosts, property types, and bedroom capacity in a visually compelling format
- Build a portfolio-ready BI asset demonstrating enterprise-grade Tableau dashboard design

---

## 📊 Dashboard Overview

### Workbook Summary

| Property | Detail |
|---|---|
| **File** | `Airbnb_Analysis_v2024_1.twbx` |
| **Tableau Version** | Tableau 2024.1 (build 20242.24.0807) |
| **Published** | Tableau Public — vizhub/workbooks/AirbnbAnalysis |
| **Dashboard Canvas** | 1,500 × 800 px (fixed widescreen layout) |
| **Design Theme** | Dark background + coral-red (`#e15759`) title bands + white typography |
| **Total Worksheets** | 6 analytical views |
| **Total Dashboards** | 1 (unified, fully cross-filtered) |
| **Data Source** | Single flat CSV — `Airbnb_data.csv` (embedded Hyper extract) |
| **Parameters** | 1 — Review Scores threshold (range: 20–100) |
| **Cross-Filter Actions** | 5 auto-generated interactive filter actions |

### Six Embedded Worksheets

| # | Sheet Name | Chart Type | Primary Business Question |
|---|---|---|---|
| 1 | **Avg. Listing Price** | Geographic Map (choropleth + bubble overlay) | Where are the most expensive Airbnb markets globally? |
| 2 | **Avg. Availability in each Country** | Highlighted table (square marks) | Which countries have the most / least calendar availability? |
| 3 | **Top 10 Hosts by Listings** | Horizontal ranked bar chart | Who are the dominant host operators and what do they charge? |
| 4 | **Top 10 Property Types** | Horizontal bar chart (room-type coloured) | Which property configurations attract the most listings? |
| 5 | **Hotels with most Bedrooms** | Treemap (square marks with multi-metric labels) | Which individual properties offer highest capacity + best reviews? |
| 6 | **Total Reviews in each Countries** | Doughnut chart (dual-axis construction) | How is global review volume distributed by country and room type? |

---

## 📋 Dataset & Data Source

### Source

| Property | Details |
|---|---|
| **File** | `Airbnb_data.csv` (embedded in `.twbx` Hyper extract) |
| **Type** | Single flat-file CSV, one table |
| **Granularity** | One row per Airbnb listing |
| **Geographic Scope** | Global multi-country (ISO3166-2 country codes) |
| **Total Columns** | 31 fields |

### Field Inventory

#### Dimensions (Categorical / Identifier)

| Field | Type | Description |
|---|---|---|
| `Id` | Integer | Unique listing identifier |
| `Listing_url` | String | Direct URL to the Airbnb listing page |
| `Name` | String | Listing title as displayed to guests |
| `Description` | String | Full listing description text |
| `House_rules` | String | Host-specified guest rules |
| `Property_type` | String | Property category (Apartment, House, Hotel, Villa, etc.) |
| `Room_type` | String | Room configuration (Entire home/apt, Private room, Shared room) |
| `Bed_type` | String | Bed configuration (Real Bed, Futon, Couch, etc.) |
| `Cancellation_policy` | String | Policy tier (Flexible, Moderate, Strict, Super Strict) |
| `Country` | String | Host country (ISO3166-2 geographic semantic role assigned) |
| `Country_code` | String | ISO country abbreviation |
| `Location_type` | String | Geographic classification |
| `Is_location_exact` | Boolean | Whether coordinates represent the exact listing location |
| `Host_id` | Integer | Unique host identifier |
| `Host_name` | String | Host display name |
| `Street` | String | Street-level location descriptor |
| `Amenities` | String | Comma-separated list of property amenities |

#### Measures (Quantitative)

| Field | Type | Description |
|---|---|---|
| `Price` | Real (USD) | **Primary KPI** — nightly listing rate |
| `Security_deposit` | Real (USD) | Required security deposit |
| `Cleaning_fee` | Real (USD) | One-time cleaning fee charged to guests |
| `Extra_people` | Real (USD) | Additional charge per extra guest beyond included count |
| `Guests_included` | Real | Guests included in base nightly price |
| `Accomodates` | Integer | Maximum guest capacity |
| `Total_bedrooms` | Real | Number of bedrooms |
| `Total_beds` | Real | Total number of beds available |
| `Min_nights` | Integer | Minimum required booking duration |
| `Max_nights` | Integer | Maximum allowed booking duration |
| `Availability_365` | Integer | Days the listing is open to booking in a year |
| `No_of_reviews` | Integer | Cumulative guest review count |
| `Review_scores` | Integer | Aggregate guest satisfaction score (out of 100) |
| `Latitude` | Real | Geographic coordinate |
| `Longitude` | Real | Geographic coordinate |

### Calculated Fields

| Field | Formula | Purpose |
|---|---|---|
| `Doughnut` | `MIN(1)` | Dual-axis inner-ring construction for doughnut chart effect |
| `Review scores Parameter` | Parameter (integer, 20–100, default 20) | Dynamic threshold filter for minimum review quality |

### Key Data Boundaries

| Metric | Value |
|---|---|
| Minimum average price (filter floor) | **~$67.44 / night** |
| Maximum average price (filter ceiling) | **~$770.96 / night** |
| Review score parameter range | **20 to 100** |

---

## 📐 KPIs & Metrics

### Primary KPIs Tracked Across the Dashboard

| KPI | Underlying Measure | Aggregation | Visual Used |
|---|---|---|---|
| **Average Nightly Listing Price** | `Price` | `AVG` | Geographic map (bubble size + red-black colour intensity) |
| **Average Availability (Days/Year)** | `Availability_365` | `AVG` | Country highlight table (red-green diverging colour) |
| **Total Listings per Host** | `Name` | `COUNT DISTINCT` | Ranked bar chart — Top 10 Hosts |
| **Listings per Property Type** | `Id` | `COUNT` | Ranked bar chart — Top 10 Property Types |
| **Total Bedroom Capacity** | `Total_bedrooms` | `SUM` | Treemap (tile size + green-blue-white colour) |
| **Total Review Volume** | `No_of_reviews` | `SUM` | Doughnut chart (slice size per country) |
| **Average Review Score** | `Review_scores` | `AVG` | Doughnut chart labels + Treemap text overlay |

### Multi-Metric Label Card (Treemap — Hotels with most Bedrooms)

Each treemap tile simultaneously displays four contextual metrics per property:

```
[Property Name] — (Score - [Review Score])

Bedrooms - [Total Bedrooms]

(Min [Min Nights] to [Max Nights] Nights)
```

This transforms a single chart into a **mini-profile card** for each high-capacity property — enabling stakeholders to assess capacity, quality, and stay policy at a glance.

### Price Benchmarks Built Into Dashboard Filters

The dashboard's cross-filter price slider is pre-calibrated to the dataset's actual price range:
- **Budget segment:** $67 – $150/night
- **Mid-market segment:** $150 – $350/night
- **Premium segment:** $350 – $600/night
- **Luxury segment:** $600 – $770+/night

---

## 🖥️ Dashboard Walkthrough

*Reading the dashboard as a stakeholder presentation — each view, its context, and the decisions it enables.*

---

### 📍 View 1 — Global Price Intelligence Map: "Avg. Listing Price"

**Chart Type:** Dual-layer geographic map — country polygon choropleth + price-encoded bubble overlay
**Colour Palette:** Red-Black sequential (Red-Black 10) — lighter = lower price, darker = higher price
**Size Encoding:** Bubble size proportional to Average Price
**Interaction:** Click any country to cross-filter all other five views instantly

The dashboard's **hero visual** — a world map where every Airbnb-listed country is rendered as a coloured polygon overlaid with price-intensity bubbles. The red-black gradient immediately reveals global pricing corridors: premium markets (US, Western Europe, Australia) emerge as large, dark circles; emerging markets appear as small, light ones. The dual-layer design — choropleth beneath, circles above — provides both geographic context and precise price ranking simultaneously.

**Decisions this enables:**
- Investors identify which countries represent high-yield vs. emerging markets
- Revenue managers benchmark their market's price position vs. global peers
- Platform analysts assess geographic pricing diversity and concentration risk

---

### 📊 View 2 — Country Availability Intelligence: "Avg. Availability in each Country"

**Chart Type:** Square-mark highlighted table (treemap-style layout)
**Colour Palette:** Red-Green Diverging — Red = low availability (high demand), Green = high availability (over-supply risk)
**Labels:** Average Availability (days/year) + Average Price shown per country cell
**Interaction:** Responds to country cross-filter from the map

Each country is represented as a labelled square, colour-coded to instantly reveal whether listings in that market are heavily booked (red) or sitting with open calendar days (green). Average price is overlaid, allowing the viewer to spot the crucial strategic relationship: are expensive markets also heavily booked (healthy, high-demand), or does high availability suggest the price is above the market-clearing level?

**Decisions this enables:**
- Markets with **red cells + high prices** = genuine high-demand premium segments (prioritise)
- Markets with **green cells + low prices** = over-supplied or low-demand markets (avoid)
- Hosts benchmark their own availability against their country's average to calibrate pricing

---

### 🏆 View 3 — Host Market Share Leaderboard: "Top 10 Hosts by Listings"

**Chart Type:** Horizontal ranked bar chart
**X-axis:** Count of listings (Count Distinct of `Name` per `Host_name`)
**Colour Encoding:** Average Price per host (red-black gradient)
**Labels:** Listing count + Average Price per bar
**Filter:** Top-10 by listing count, descending

The definitive leaderboard of Airbnb's most prolific operators. Bar length shows listing volume; bar colour reveals pricing tier. A **dark, long bar** = a professional high-volume, high-price operator. A **light, long bar** = a volume competitor who wins on scale but not price. This bifurcation tells the market structure story: is this a market dominated by individual hosts, or have professional management companies consolidated supply?

**Decisions this enables:**
- Individual hosts understand who they're competing against and at what pricing tier
- Platform analysts identify super-host operators and professional property management companies
- Investors assess whether the market is fragmented (many small hosts = easier to enter) or consolidated (few powerful operators = higher barriers)

---

### 🏘️ View 4 — Property Type Supply Analysis: "Top 10 Property Types"

**Chart Type:** Horizontal ranked bar chart
**X-axis:** Count of listings (Count of `Id` per `Property_type`)
**Colour Encoding:** Room type within each property type (Watermelon palette — distinct for Entire home/apt, Private room, Shared room)
**Interaction:** Cross-filtered by country and price range

The supply-side property landscape — which property configurations dominate the Airbnb listing market. Each bar is colour-segmented by Room Type, revealing not just listing counts per property category but the room-configuration mix within each type. A bar dominated by Entire home/apt colour signals a full-home rental market in that property type; Private room dominance indicates a co-living or budget market.

**Decisions this enables:**
- New hosts choose which property type to list based on market saturation signals
- Platform analysts monitor room-type mix for regulatory risk assessment (entire-home listings attract most regulation)
- Investors structure acquisitions around the most demand-rich and competitively rational property type

---

### 🛏️ View 5 — High-Capacity Property Treemap: "Hotels with most Bedrooms"

**Chart Type:** Treemap (square marks), Top-10 filter by SUM(Total_bedrooms) descending
**Colour Palette:** Green-Blue-White Diverging — more bedrooms = deeper green/blue tile
**Size Encoding:** Tile area proportional to total bedrooms
**Multi-metric label:** Property Name + Review Score + Total Bedrooms + Min–Max Night window
**Filter:** Top 10 properties by bedroom count globally (or within selected country)

The highest-capacity individual Airbnb properties on the platform — hotels, villas, and estate-type listings that dwarf typical apartments. Each tile carries four data points simultaneously: a **large, deep-blue tile with a high review score** is the benchmark — high capacity managed at hotel-grade quality. A **large but lightly-coloured tile** may carry quality concerns reflected in lower review scores or restrictive stay policies.

**Decisions this enables:**
- Group travel organisers identify the best high-capacity properties for retreats, weddings, corporate events
- Platform strategists assess whether large-property supply is growing and whether quality is maintained at scale
- Property managers benchmark their bedroom count and review scores against market top-10 performers

---

### 🍩 View 6 — Review Distribution Doughnut: "Total Reviews in each Countries"

**Chart Type:** Doughnut chart (dual-axis MIN(1) ring construction using Pie marks)
**Colour Encoding:** Country (Jewel Bright palette — vivid distinct colours per country)
**Slice Size:** Sum of `No_of_reviews` per country per room type column
**X-axis split:** Room Type (Entire home/apt, Private room, Shared room as separate doughnut columns)
**Labels:** Country name + Sum Reviews + Average Review Score

A visually rich breakdown of where Airbnb's global guest review activity is concentrated. Each doughnut slice represents a country's share of total reviews for a given room type. Countries with thick slices have the most engaged guest communities — markers of mature, high-traffic Airbnb ecosystems. The average review score label provides a quality overlay: **high review volume + high average score = a healthy, thriving market**. A country with high volume but low average score signals systemic guest satisfaction issues.

**Decisions this enables:**
- Platform analysts track market maturity — thick slices with high scores identify Airbnb's core revenue ecosystems
- Quality managers flag countries with high volume but deteriorating average scores for targeted intervention
- Hosts use review volume by country as a proxy for booking frequency and market demand intensity

---

## 💡 Key Insights

> *Translating visual patterns into strategic business intelligence.*

**1. Global Pricing Is Structured in Clear Corridors — A ~11× Spread Exists**
The choropleth price map reveals an approximately 11× pricing multiple between the platform's cheapest and most expensive country-average markets ($67 to $770/night). This is not random variation — it reflects deeply structural differences in local real estate costs, tourism demand intensity, and regulatory environments. Investors and hosts cannot apply a single global pricing strategy; country-calibrated pricing is essential.

**2. High Availability ≠ Market Health — Many Markets Are Over-Supplied**
The red-green availability table exposes a critical disconnect in several markets: countries showing green (high open calendar days) combined with low average prices are exhibiting the classic signature of over-supply — too many listings competing for too few guests. Markets where availability is consistently red (low open days) represent genuinely demand-constrained inventory — the healthiest signal for existing and prospective hosts.

**3. Professional Operators Have Consolidated Top-Market Host Leaderboards**
The Top 10 Hosts chart confirms that high-volume hosts in mature markets are overwhelmingly professional property management companies — not individual landlords. This structural shift means individual hosts in these markets are competing against sophisticated operators with dynamic pricing tools, professional photography, and optimised guest communication workflows. Individual hosts must compete on authenticity, uniqueness, and superior personalised service — not price or volume.

**4. A Small Number of Property Types Capture the Majority of Listings**
The property type chart shows a classic long-tail supply distribution. A handful of categories (Apartments, Houses, Condominiums, Hotels) dominate listing counts, while dozens of niche types (Villas, Boats, Treehouses, Yurts) represent a tiny fraction. Within dominant types, Entire home/apt configurations command premium positioning; Private room listings anchor the budget-accessible tier. New hosts entering oversaturated property types should differentiate on room configuration and amenities, not listing volume.

**5. High Bedroom Count Does Not Guarantee High Review Scores**
The bedroom treemap reveals that the largest-tile properties (highest bedroom counts) do not uniformly carry the highest review scores. Several large-scale properties show moderate scores — evidence that scaling physical capacity without investing in hospitality operations quality produces guest experience degradation. The highest-performing large properties (large tile + high score + reasonable stay window) represent the benchmark for professional Airbnb property management.

**6. Review Volume Concentration Reveals Platform's Core Economic Ecosystems**
The doughnut chart confirms that global review activity — a reliable proxy for booking frequency — is concentrated in a small number of countries. These thick-sliced markets are Airbnb's revenue engine. A platform health crisis in any of these core geographies would have outsized impact on overall booking volumes. For hosts, being in a thick-slice country market means high competition but also high demand.

**7. Cross-Filtering Reveals Country-Specific Market Structures Invisible at Global Level**
When the country cross-filter is applied via the map, each individual view reconfigures completely: host rankings, property type mix, availability patterns, and review distributions all shift dramatically between geographies. This confirms that Airbnb is not a single homogeneous market — it is a collection of dozens of distinct local markets, each requiring its own analytical lens and business strategy.

---

## 💼 Business Recommendations

**1. Use the Availability-Price Quadrant to Prioritise Market Entry**
Combine the Availability view (red = low availability) and Price map (dark = high price) to identify the optimal market entry quadrant: **low availability + high price = high-demand premium market**. Use the country cross-filter to drill into these markets and assess host competition (View 3) and property type saturation (View 4) before committing investment.

**2. Benchmark Listing Price Within 10–15% of Country Average — But Segment by Room Type**
The geographic price map's average bubbles should serve as the reference anchor for any pricing decision. However, the correct benchmark is not the country average alone — it must be segmented by room type (Entire home vs. Private room) and property type. Use the price filter to isolate listings in your tier and the property type chart to understand competitive density before setting a final rate.

**3. In Top-Host-Dominated Markets, Compete on Review Score — Not Volume**
Where the host leaderboard shows professional operators with 50+ listings, individual hosts cannot compete on scale or price efficiency. The strategic winning move is driving review scores to the top quartile for the country (visible in the doughnut chart's average score labels). Review score-driven algorithmic ranking improvement is the primary lever for individual hosts to increase visibility against professional competitors.

**4. Match Property Type Strategy to the Room-Type Colour Mix in Target Country**
After filtering to a target country using the map cross-filter, examine the Property Type chart for room-type colour distribution within each property category. If Entire home/apt (the highest-priced tier) dominates the top property types, that market already commands premium pricing — enter with premium positioning or avoid saturation. If Private room colours dominate, the market is price-accessible but margin-compressed.

**5. Large-Capacity Properties Must Invest in Operational Quality Commensurate With Scale**
The bedroom treemap consistently shows that review score performance does not automatically scale with bedroom count. Any operator managing properties with 10+ bedrooms should benchmark their review score against the top-10 treemap performers before scaling further. Under-investment in housekeeping, maintenance, and guest communication at scale produces review score deterioration that compresses future pricing power and booking frequency.

**6. Use Review Volume by Country as a Demand Signal Before Setting Calendar Availability**
The doughnut chart's review volume by country is a leading indicator of booking frequency in that market. Hosts in high-review-volume countries (thick slices) can afford more restrictive minimum nights policies because demand is high enough to fill gaps. Hosts in thin-slice countries should maintain high calendar availability and flexible booking policies to maximise occupancy in lower-demand environments.

**7. Monitor Average Review Score Trends by Country as a Platform Health KPI**
The average review scores shown in the doughnut chart should be monitored over time as Airbnb's primary guest satisfaction metric. A country where review volume is growing but average score is declining signals an influx of lower-quality listings outpacing demand — a leading indicator of future churn from repeat guests. Platform managers should prioritise host quality programmes in these markets before review scores deteriorate further.

---

## 🛠️ Tableau Features Used

### Interactivity & Filtering

| Feature | Implementation | Business Value |
|---|---|---|
| **Cross-Filter Dashboard Actions** | 5 auto-generated filter actions connecting all 6 sheets via `Country`, `Name` | Single click on any mark filters the entire dashboard — geographic, listing, and host-level drill-down without leaving the view |
| **Price Range Slider Filter** | Continuous range filter on `AVG(Price)`: min $67.44, max $770.96, applied to all worksheets | Analysts dynamically isolate budget, mid-market, and premium segments; all 6 views update simultaneously |
| **Review Scores Parameter** | Integer parameter (range 20–100, default 20) | Controls minimum review quality threshold — surfaces only high-rated listings across all views when adjusted |
| **Top-N Filters** | Count=10 on Hosts (by listing count DESC) and Properties (by total bedrooms DESC) | Auto-ranks the 10 most relevant performers dynamically; responds to country cross-filter |

### Visualisation Techniques

| Technique | Sheet | Technical Detail |
|---|---|---|
| **Dual-Layer Geographic Map** | Avg. Listing Price | Multipolygon country choropleth + bubble overlay using `([Latitude] + [Latitude])` dual-fold ROWS axis; EPSG:3857 Web Mercator projection |
| **Doughnut Chart Construction** | Total Reviews | Dual-axis Pie chart with `Doughnut` = `MIN(1)` calculated field creating the inner transparent ring; Room Type on Columns creates side-by-side doughnut columns |
| **Treemap via Square Marks** | Hotels with most Bedrooms + Availability | Square mark type with Size and Colour encoding — no native treemap required; creates proportional area layout naturally |
| **Multi-Metric Label Cards** | Hotels with most Bedrooms | Custom formatted label string renders 4 metrics (Name, Score, Bedrooms, Min–Max Nights) as a mini property card on each treemap tile |
| **Diverging Colour Palettes** | Availability (Red-Green), Bedrooms (Green-Blue-White) | Encodes directionality — red signals alert / low, green signals positive / high — for immediate visual parsing without legend reading |
| **Sequential Price Colour on Bars** | Top 10 Hosts | Red-Black sequential palette on bar fill adds a second data dimension (Avg Price) to a ranked bar chart without adding additional marks |
| **Room Type Colour Split in Bars** | Top 10 Property Types | Watermelon (`sf_watermelon`) categorical palette segments each bar by Room Type, converting a single-dimension bar chart into a stacked composition view |

### Calculated Fields

| Field | Formula | Technical Purpose |
|---|---|---|
| `Doughnut` | `MIN(1)` | Returns 1 for every mark — used as the outer measure in the dual-axis doughnut construction; the inner axis (also MIN(1)) creates the transparent ring when the inner pie is formatted with white fill and no border |
| `Review scores Parameter` | Tableau integer parameter | Connected to filter logic to exclude listings below the selected review score threshold; can be extended with IF/THEN calculated field logic for conditional display |

### Geographic Features

| Feature | Detail |
|---|---|
| **Country Semantic Role** | `Country` field assigned ISO3166-2 geographic semantic role — enables automatic polygon fill matching |
| **Map Projection** | EPSG:3857 (Web Mercator) — standard web cartography; consistent with Google Maps and Mapbox conventions |
| **Dual-Axis Map Trick** | `([Latitude (generated)] + [Latitude (generated)])` on ROWS creates two independent mark layers on the same map canvas — one for polygon fill, one for bubble overlay |

### Design Choices

| Element | Implementation | Rationale |
|---|---|---|
| **Background image** | `Sales_bg.jpg` — dark textured background fills the canvas | Professional aesthetic; improves contrast for bright chart colours and reduces visual fatigue on widescreen displays |
| **Title graphic** | `title.png` — custom branded title banner | Consistent with enterprise BI standards; avoids Tableau's default title formatting |
| **Coral-red title bands** | `#e15759` header background + white bold Tableau Bold 14pt text | High-contrast section labelling; Airbnb brand-adjacent colour (Airbnb's primary red is `#FF5A5F`) |
| **Fixed canvas** | 1,500 × 800 px | Widescreen optimised for 16:9 presentation displays and Tableau Public embedding |
| **Jewel Bright palette** | Country colours in doughnut chart | High-contrast, visually distinct multi-country categorical differentiation at a glance |

---

## ▶️ How to Use

### Prerequisites

- **Tableau Desktop 2024.1** or later (recommended for full interactivity)
- **Tableau Reader** (free download from Tableau) — view-only mode
- **Tableau Public** (browser-based, no installation) — free access

### Opening the Dashboard

**Option 1 — Tableau Desktop / Reader:**
```
1. Download Airbnb_Analysis_v2024_1.twbx from this repository
2. Double-click the .twbx file — Tableau opens automatically
3. The embedded .hyper extract loads instantly — no external connection needed
4. Click "Dashboard 1" tab at the bottom of the screen
5. Full interactivity available immediately
```

**Option 2 — Tableau Public (Browser, No Installation):**
```
1. Go to public.tableau.com
2. Search: "AirbnbAnalysis_17246562109740" or "Vishal Londhekar Airbnb"
3. Click the published workbook to open in the browser
4. All cross-filter interactions work natively in the browser
```

### Interacting with the Dashboard

**Cross-filter by Geography (Map → All Views):**
```
→ Click any country polygon or bubble on the Avg. Listing Price map
→ All 5 other views instantly filter to show only that country's data
→ Click again or press Escape to clear the geographic filter
```

**Apply Price Range Filter:**
```
→ Locate the price range slider (continuous filter control)
→ Drag the left handle right to raise the minimum price floor
→ Drag the right handle left to lower the maximum price ceiling
→ All 6 views update dynamically to the selected price bracket
```

**Adjust Review Score Threshold:**
```
→ Find the "Review scores Parameter" control (range slider: 20–100)
→ Increase the minimum to filter for only high-quality listings (e.g., set to 80)
→ Dashboard recalculates all aggregations to exclude sub-threshold listings
```

**Drill to Individual Property:**
```
→ Click any tile in the "Hotels with most Bedrooms" treemap
→ Cross-filter propagates to reveal that property's country context in the map
→ The host leaderboard and property type chart filter to the property's country
→ The doughnut chart highlights that country's review share
```

**Hover for Tooltip Details:**
```
→ Hover over any map bubble to see Country name + Avg Price
→ Hover over any treemap tile to see Property Name, Score, Bedrooms, Min–Max Nights
→ Hover over any bar to see Host Name / Property Type + Listing Count + Avg Price
→ Hover over any doughnut slice to see Country + Review Count + Avg Score
```

---

## 📁 Project Structure

```
Airbnb-Tableau-Dashboard/
│
├── Airbnb_Analysis_v2024_1.twbx           # Packaged Tableau workbook (self-contained)
│   ├── Airbnb Analysis.twb                # Tableau workbook XML definition
│   ├── Data/
│   │   └── #TableauTemp_*.hyper           # Embedded Hyper data extract (no external DB needed)
│   └── Image/
│       ├── Sales_bg.jpg                   # Dashboard dark background texture
│       └── title.png                      # Custom branded title graphic
│
├── screenshots/                           # (Recommended) Export dashboard views as PNG
│   ├── dashboard_full.png                 # Full 1500×800 dashboard screenshot
│   ├── map_price_view.png                 # Geographic price map close-up
│   ├── host_ranking.png                   # Top 10 Hosts bar chart
│   ├── bedroom_treemap.png                # Hotels with most Bedrooms treemap
│   ├── availability_table.png             # Country availability highlight table
│   ├── property_types.png                 # Top 10 Property Types chart
│   └── reviews_doughnut.png               # Total Reviews doughnut chart
│
└── README.md                              # Project documentation (this file)
```

### Worksheet Reference

| Tab Name | Visible Title | Visual Type |
|---|---|---|
| `Avg. Listing Price` | Global Price Map | Dual-layer geographic map |
| `Avg. Availability in each Country` | Country Availability | Highlighted square-mark table |
| `Top 10 Hosts by Listings` | Host Leaderboard | Horizontal ranked bar chart |
| `Top 10 Property Types` | Property Type Mix | Horizontal bar chart (room-type coloured) |
| `Sheet 6` | Hotels with most Bedrooms | Treemap with multi-metric labels |
| `Total Reviews in each Countries` | Review Distribution | Doughnut chart (dual-axis construction) |
| **`Dashboard 1`** | **Main Dashboard View** | **All 6 views, fully cross-filtered** |

---

## 👤 Author

<table>
  <tr>
    <td align="center">
      <b>Vishal Londhekar</b><br/>
      <i>Data Analyst | Business Analyst | Data Scientist</i><br/><br/>
      <a href="https://github.com/vishal-Londhekar">🔗 GitHub</a>&nbsp;&nbsp;
      <a href="https://public.tableau.com/app/profile/vishal.londhekar">📊 Tableau Public</a>
    </td>
  </tr>
</table>

> *"A great BI dashboard doesn't just answer the questions stakeholders have — it reveals the questions they didn't know they needed to ask."*

---

## ⭐ If this dashboard inspired your own Tableau work, please star the repository!

---

<p align="center">
  <img src="https://img.shields.io/badge/Built%20with-Tableau%202024.1-blue?logo=tableau" />
  <img src="https://img.shields.io/badge/Domain-Airbnb%20%7C%20Short--Term%20Rental-orange" />
  <img src="https://img.shields.io/badge/Views-6%20Cross--Filtered%20Charts-brightgreen" />
  <img src="https://img.shields.io/badge/Map-Global%20Choropleth%20%2B%20Bubbles-red" />
  <img src="https://img.shields.io/badge/Chart-Treemap%20%7C%20Doughnut%20%7C%20Bar-blueviolet" />
</p>
