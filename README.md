# 📊 Financial Performance Dashboard (Power BI)

An interactive Power BI dashboard that tells the story of **19K customers and 31K orders** across **3 regions and 10 territories**, selling **Bikes, Components, Clothing and Accessories** between **2011 and 2014**. Instead of staring at tables, the dashboard answers real questions: Where does the money come from? Where do we lose it? What actually drives profit up or down? Are discounts helping or hurting?

<img width="1516" height="758" alt="image" src="https://github.com/user-attachments/assets/4b87d327-c126-4e53-aba8-ef68c0d2fd45" />


---

## 🗂️ Project Contents

| File | Description |
|---|---|
| `FinancialDashboard.pbix` | The complete Power BI report |
| ↳ **Financial Dashboard** page | Page 1 – overview (KPIs, trends, products, regions, stock) |
| ↳ **KeyInfluenceToProfit** page | Page 2 – AI-driven analysis of what moves profit (Key Influencers + Top Segments) |
| ↳ **TreeMap** page | Page 3 – sales weight of every product subcategory |
| ↳ **DecompositionTree** page | Page 4 – customers and orders broken down by region |
| `images/` | Dashboard screenshots |
| `data/` | The dataset |

**Data columns used in the report:** Region Group · Region Name · Product Category · Product Subcategory · ProductStatus · Year / Month · OrderQty · totalOrderWithDiscount · totalOrderWithoutDiscount · totalRealSales · realprofit · grossProfitperProduct · Loss · Customer · Order

---

## ❓ Questions This Dashboard Answers

### Page 1: Overview
KPI cards: *"Where do we stand right now?"*

- The company has **19K customers** and **31K orders**.
- It generated **$165.37M** in real sales.
- But the profit margin is only **3.38%**.

| Chart | Question | Short Answer |
|---|---|---|
| Orders by Year (line) | Is the business growing? | Strong growth 2011 → 2013, then a sharp drop in 2014 (possibly an incomplete year). |
| Sales & Profit by Category | Which category carries the business? | **Bikes** dominate by a wide margin; Components are a distant second. |
| Top Product Per Profit | Which products make the most profit? | Road Bikes (25.9K), Mountain Bikes (23.9K), Touring Bikes (11.9K). |
| Sales per Region (map) | Where do we sell most? | North America, led by the Southwest. |
| Loss Profit table | Where are we losing money? | Southwest, Australia and Northwest lose the most. |
| Stock status (pie) | How healthy is the inventory? | 66.78% in stock, 33.22% out of stock. |

### Page 2: KeyInfluenceToProfit
| View | Question | Short Answer |
|---|---|---|
| Key Influencers – Increase | What makes profit go **up**? | Order value between **$1,828 and $2,195**. |
| Key Influencers – Decrease | What makes profit go **down**? | Small orders (**≤ $431**) and very large quantities (**> 11 units**). |
| Top Segments – High | Which groups are the most profitable? | 3 segments, the best averaging **191** profit per record. |
| Top Segments – Low | Which groups are the least profitable? | 4 segments, the biggest averaging only **3.09**. |

### Page 3 & 4: Deep Dives
| Chart | Question | Short Answer |
|---|---|---|
| TreeMap | Which subcategories drive sales after discount? | Road Bikes and Mountain Bikes take up most of the map. |
| Decomposition Tree – Customers | Where are our customers? | North America (9,887) → Europe (5,607) → Pacific (3,625). |
| Decomposition Tree – Orders | Where do orders come from? | North America (16,108), led by Southwest (6,224). |

### Questions That Emerge From Combining Charts
- **Are our biggest markets also our biggest loss-makers?** Yes. Southwest, Northwest and Canada lead in sales *and* in losses.
- **Are discounts and order size hurting profit?** Yes, small orders and bulk orders both reduce profit, while mid-to-high-value orders increase it.
- **Are we too dependent on one product line?** Yes. Bikes carry the business.

> 💡 The slicers let you ask any of these questions for a specific slice, for example: *"What does the picture look like for Bikes in Europe, in stock products only?"*

---

## 🎨 Dashboard Design

The dashboard follows a clean, consistent **green corporate theme** so the numbers stay the focus and nothing competes for attention.

| Role | Color | Where it's used |
|---|---|---|
| Header banner & filter panel | Deep forest green | Title bar and left-side filters, with white bold text |
| KPI cards | White with green border | Large dark-green values with soft teal labels |
| Chart titles | Dark green bars | Clear, uniform headers on every visual |
| Chart series | Dark green + light sage | Two-tone lines and bars |
| Page background | Pale grey / sage | Soft canvas that lets the cards stand out |

### Navigation
Three buttons in the header (**KeyInfluence**, **DecompositionTree**, **TreeMap**) open the deep-dive pages, and a back arrow on each page returns to the main dashboard.

---

## 🎛️ Filters (Slicers), Left Side of the Main Page

| Slicer | Purpose |
|---|---|
| **Month** | Zoom in on a specific month |
| **Product Category** | Bikes / Components / Clothing / Accessories |
| **Region Group** | North America / Europe / Pacific |
| **ProductStatus** | InStock / OutOfStock |

> 💡 **Try it:** select *Region Group = Europe* and *Product Category = Bikes* and watch the whole dashboard retell the story for just that slice.

---

## 📄 Page 1: Financial Dashboard (Overview)

### 🔢 Part 1: KPI Cards

**The story:** The moment you open the dashboard, these numbers tell you "where we stand" in five seconds.

| Card | Value | The Story |
|---|---|---|
| 👥 NumberOfCustomer | **19K** (19,119) | The size of the customer base. |
| 🛒 NumberOfOrders | **31K** (31,465) | About 1.65 orders per customer, so most customers don't come back many times. |
| 💰 totalRealSales | **165.37M** | The scale of the business. |
| 🏷️ ValueofDiscounts > 200 | **2.73M** | Discounts above 200 add up to a significant amount, so discount policy is worth watching. |
| 📈 Profit Percentage | **3.38%** | The key warning sign: a big sales number, but only about 3 cents of profit on every dollar. |

---

### 📈 Chart 1: Orders With vs Without Discount by Year
**Type:** Line chart · **Question:** Is the business growing, and does the discount change the picture?

**The story:** Sales grew sharply from roughly **$18M in 2011** to about **$55M in 2012** and peaked near **$68M in 2013**. Then 2014 drops back to about **$27M**.

The two lines (with and without discount) sit very close together, so the discount doesn't change the *shape* of sales. Its real impact shows up in **profit**, not revenue.

> ⚠️ **Takeaway:** The 2014 drop may be a partial year rather than a real decline. Confirm the date range of the data before drawing conclusions.
> *(Values are read from the chart and are approximate.)*

---

### 🚲 Chart 2: Total Real Sales & Total Real Profit by Product Category
**Type:** Column + line combo · **Question:** Which category carries the business?

**The story:** **Bikes** reach roughly **$140M+**, around 85% of total sales. **Components** follow with about **$20M**, while **Clothing** and **Accessories** are almost invisible next to them. The profit line falls off in the same pattern.

> **Takeaway:** The company is essentially a bike company. That is a strength, but also a **concentration risk**: a weak year for bikes hits the whole business.

---

### 🏆 Chart 3: Top Product Per Profit
**Type:** Table · **Question:** Which products make the most profit?

| Category | Subcategory | Gross Profit |
|---|---|---|
| Bikes | **Road Bikes** | 25,968.72 |
| Bikes | **Mountain Bikes** | 23,987.04 |
| Bikes | Touring Bikes | 11,864.91 |
| Components | Road Frames | 9,889.01 |
| Components | Mountain Frames | 8,772.89 |
| Components | Touring Frames | 4,553.01 |
| Components | Wheels | 1,719.71 |
| Components | Cranksets | 465.36 |
| Components | Handlebars | 328.66 |
| Components | Forks | 307.58 |

**The story:** The three bike types and the frames bring in almost all of the profit. Accessories like Cranksets, Handlebars and Forks add very little.

> **Takeaway:** Protect Road and Mountain Bikes first; they are the profit engine.

---

### 🌍 Chart 4: Total Real Sales per Region (Map)
**Type:** Map · **Question:** Where do we sell the most?

**The story:** The biggest bubbles are in **North America** (Southwest, Northwest, Canada), followed by **Europe** (UK, France, Germany) and **Australia**.

> ⚠️ Power BI shows a notice that this map visual is being retired. Consider migrating it to the newer **Azure Map** visual.

---

### 🔴 Chart 5: Loss Profit by Region
**Type:** Table · **Question:** Where are we losing money?

| Region Group | Region | Loss |
|---|---|---|
| North America | **Southwest** | $1,145,884 |
| Pacific | **Australia** | $971,189 |
| North America | **Northwest** | $730,434 |
| North America | Canada | $650,326 |
| Europe | United Kingdom | $440,278 |
| Europe | France | $379,784 |
| Europe | Germany | $345,034 |
| North America | Southeast | $285,943 |
| North America | Central | $244,190 |
| North America | Northeast | $237,371 |

**The story:** Together these add up to about **$5.4M in losses**, which is why the profit margin is so thin.

Notice that **Southwest, Northwest and Canada** are also among the biggest markets for orders. The regions that sell the most also lose the most.

> **Takeaway:** The problem is probably not a lack of demand. It points to **pricing, discounts or cost** in the biggest markets.

---

### 📦 Chart 6: Product Subcategory Count by Product Status
**Type:** Pie chart · **Question:** How healthy is the inventory?

**The story:** **197 products (66.78%) are in stock** and **98 (33.22%) are out of stock**.

> **Takeaway:** One out of every three products is unavailable. If these are high-demand items, that is **lost sales**.

---

## 📄 Page 2: KeyInfluenceToProfit
##Increase

<img width="1339" height="749" alt="image" src="https://github.com/user-attachments/assets/f273286c-f150-4537-9c94-c3d32efc4462" />

<img width="1340" height="750" alt="image" src="https://github.com/user-attachments/assets/a088651e-67d9-4166-9797-49f9b549c2ae" />

<img width="1335" height="749" alt="image" src="https://github.com/user-attachments/assets/e1bb1879-8849-4ccf-8e66-b9abc6703e98" />

##Decrease

<img width="1338" height="750" alt="image" src="https://github.com/user-attachments/assets/a9da36cb-6e1a-4c84-ba25-e78504aca917" />

<img width="1344" height="744" alt="image" src="https://github.com/user-attachments/assets/52c51517-b2ef-41a7-be07-4e206f7da256" />

<img width="1347" height="753" alt="image" src="https://github.com/user-attachments/assets/aba64524-14b5-4e36-a8a6-b6a6fcbbf26a" />



### ⬆️ What Increases Profit?

| Condition | Average Profit Increase |
|---|---|
| Order value (with discount) between **$1,828 and $2,195** | **+217.2** ⭐ |
| Order value **above $2,195** | +88.55 |
| Order value between **$903 and $1,828** | +19.45 |

**The story:** Profit rises as order value rises, and the **sweet spot is the $1,828 – $2,195 range**. Above that range it is still positive but much lower, which may point to heavier discounting on the biggest orders.

![Key Influencers - Decrease](images/04_key_influence_decrease.png)

### ⬇️ What Decreases Profit?

| Condition | Average Profit Decrease |
|---|---|
| Order value **$431 or less** | **-98.84** ⚠️ |
| Order quantity (OrderQty) **more than 11** | -34.95 |
| Order value between **$431 and $903** | -12.38 |

**The story:** Small orders are the biggest profit killer: handling and cost eat the margin. Very large quantities also reduce profit, which usually means deep volume discounts.

> **Takeaway:** Push customers toward mid-to-high-value orders, and review discount rules for bulk quantities.

![Top Segments - High](images/03_top_segments_high.png)

### 🎯 Top Segments

| View | Segment | Average Profit | Population |
|---|---|---|---|
| **High profit** | Segment 1 | **191** | 16,156 |
| | Segment 2 | 104.5 | 8,361 |
| | Segment 3 | 86.58 | 8,481 |
| **Low profit** | Segment 4 | 23.55 | 12,663 |
| | Segment 3 | 3.25 | 8,131 |
| | Segment 2 | **3.09** | **51,681** |
| | Segment 1 | 2.35 | 8,364 |

![Top Segments - Low](images/05_top_segments_low.png)

**The story:** There is a healthy high-profit group (Segment 1, 16K records at an average of 191). But the **largest low-profit segment contains about 51.7K records with an average profit of just 3.09**. The bulk of the activity earns almost nothing.

> **Takeaway:** Moving even part of that big low-profit segment toward the profitable pattern would change the margin dramatically.

---

## 📄 Page 3: Decomposition Tree

<img width="1338" height="745" alt="image" src="https://github.com/user-attachments/assets/0f868c3f-8e51-44f5-bd18-887b4e1765c1" />

---

## 📄 Page 4: TreeMap

<img width="1349" height="748" alt="image" src="https://github.com/user-attachments/assets/bd10b600-ec53-4c85-83f0-9e78175eb2ed" />


**Type:** TreeMap · **Question:** Which subcategories drive sales after discount?

**The story:** **Road Bikes** and **Mountain Bikes** take up the biggest blocks, followed by **Touring Bikes**, **Mountain Frames** and **Road Frames**. After that the map breaks into dozens of tiny blocks (Jerseys, Vests, Gloves, Helmets, Tires, Pedals and more).

> **Takeaway:** A handful of products make up most of the revenue, and the long tail of small items contributes very little. Worth asking whether the tail is worth its operational cost.

---

### 👥 Number of Customers per Country

| Region Group | Customers | Region | Customers |
|---|---|---|---|
| **North America** | 9,887 | | |
| **Europe** | 5,607 | United Kingdom | 1,951 |
| | | France | 1,844 |
| | | Germany | 1,812 |
| **Pacific** | 3,625 | | |
| **Total** | **19,119** | | |

### 🛒 Number of Orders per Country

| Region Group | Orders | Region | Orders |
|---|---|---|---|
| **North America** | 16,108 | Southwest | 6,224 |
| | | Northwest | 4,594 |
| | | Canada | 4,067 |
| | | Southeast | 486 |
| | | Central | 385 |
| | | Northeast | 352 |
| **Europe** | 8,514 | | |
| **Pacific** | 6,843 | | |
| **Total** | **31,465** | | |

**The story:**
- North America holds just over half of customers and orders. Inside it, three territories (Southwest, Northwest, Canada) generate **almost all** of the orders, while Southeast, Central and Northeast barely register.
- Europe is **evenly balanced** across the UK, France and Germany.
- Pacific has the fewest customers (3,625) but a high number of orders (6,843), about **1.9 orders per customer**, higher than North America (about 1.6).

> **Takeaway:** Three North American territories are underdeveloped, which is a clear growth opportunity. Pacific customers are the most loyal in terms of repeat orders.

---

## 🧩 The Whole Story in 6 Sentences

1. The company has **19K customers and 31K orders** and sells **$165M**, but keeps only a **3.38%** margin.
2. Sales grew strongly from 2011 to 2013, with a sharp drop in 2014 that needs verification.
3. **Bikes** (Road, Mountain, Touring) are the backbone of both sales and profit.
4. The biggest markets (**Southwest, Northwest, Canada**) are also among the biggest loss-makers, and Australia is a major loss area too.
5. **Order size drives profit**: orders under $431 lose money, and the sweet spot is $1,828 – $2,195.
6. One out of every three products is out of stock, and a huge low-profit segment (51K records) is waiting to be improved.

---

## 🧭 Strategic Action Plan: Strategies & Tactics

### 🎯 The Core Problem
> **A large, growing business that keeps only 3.38% of every dollar it sells.**
> Sales are high ($165.37M), but about **$5.4M in losses**, heavy discounting, tiny orders and a huge low-profit segment are eating the margin.

**Why it matters:** with $165M in sales, **every +1 percentage point of margin is worth roughly $1.65M** in extra profit. Small operational fixes can change the picture a lot.

### 🏁 Strategic Objectives

| # | Objective | Current Baseline (from the dashboard) |
|---|---|---|
| 1 | Raise the profit margin | 3.38% |
| 2 | Cut losses in the biggest markets | ≈ $5.4M total loss |
| 3 | Move orders toward the profitable value range | Orders ≤ $431 lose ~98.84 on average |
| 4 | Reduce dependency on bikes | Bikes ≈ 85% of sales |
| 5 | Improve product availability | 33.22% out of stock |
| 6 | Increase customer repeat purchases | ≈ 1.65 orders per customer |

---

### Strategy 1: Order Value Optimization 💰
**Insight:** Orders ≤ $431 reduce profit the most (-98.84). The sweet spot is **$1,828 – $2,195** (+217.2).
**Goal:** Shift the order mix upward.

| Tactic | How | Metric to Track |
|---|---|---|
| Minimum order / free-shipping threshold | Set free shipping above ~$900 so customers add items to qualify | % of orders ≤ $431 |
| Product bundles | Bike + helmet + accessories packages priced to land in the $1,800 – $2,200 range | Average order value |
| Checkout upsell / cross-sell | Suggest compatible accessories and components at checkout | Items per order |
| Tiered rewards | Reward customers for crossing value tiers instead of discounting small orders | Orders in $1,828 – $2,195 band |

---

### Strategy 2: Discount Governance 🏷️
**Insight:** Quantities above 11 units reduce profit (-34.95), and discounts above 200 total **$2.73M**. Profit above $2,195 falls back to +88.55, which suggests deeper discounts on the biggest orders.
**Goal:** Keep discounts that create volume, stop discounts that destroy margin.

| Tactic | How | Metric to Track |
|---|---|---|
| Margin-based discount caps | No discount may push an order below a minimum margin | Profit % per order |
| Approval workflow | Discounts over a set value (e.g., 200) need manager sign-off | Number / value of discounts > 200 |
| Redesign volume pricing | Find the quantity where profit turns negative (around 11 units) and flatten the discount beyond it | Profit of orders with qty > 11 |
| A/B test discount levels | Test lower discounts in a few territories and compare profit | Profit lift vs control group |

---

### Strategy 3: Fix the Loss-Making Regions 🔴
**Insight:** Southwest ($1.15M), Australia ($971K), Northwest ($730K) and Canada ($650K) lose the most, and three of them are also top-selling markets. This points to **pricing, cost or discounts**, not demand.
**Goal:** Stop selling at a loss in the biggest markets before pushing for more volume.

| Tactic | How | Metric to Track |
|---|---|---|
| Root-cause analysis per region | Drill the loss by subcategory, discount level and order size to find where it concentrates | Loss by subcategory / region |
| Regional price review | Raise prices or cut discounts on products that consistently lose money | Loss per region |
| Logistics & cost review (esp. Australia) | Check shipping and distribution costs for the Pacific region | Cost per order |
| Region profit scorecard | Add a monthly profit-by-region view with an alert when loss crosses a threshold | Monthly loss trend |

---

### Strategy 4: Convert the Big Low-Profit Segment 🎯
**Insight:** The largest low-profit segment has **51,681 records averaging only 3.09** profit, while the best segment averages **191**.
**Goal:** Move part of this segment toward the profitable pattern.

| Tactic | How | Metric to Track |
|---|---|---|
| Profile the segment | Use the Key Influencers / Decomposition Tree to find which products, regions and order sizes define it | Segment profile |
| Reprice and re-package | Apply the minimum-order and bundling tactics to this segment first | Average profit of the segment |
| Replicate the winners | Study Segment 1 (avg 191) and copy its conditions (order value, products, regions) | Share of records in high-profit segments |

---

### Strategy 5: Grow Smart in Under-Penetrated Territories 🌍
**Insight:** Southeast (486), Central (385) and Northeast (352) have very few orders compared with Southwest (6,224).
**Goal:** Expand only after unit economics are healthy.

> ⚠️ **Sequence matters:** growing in markets where we lose money just grows the loss. Fix Strategies 1–3 first, then expand.

| Tactic | How | Metric to Track |
|---|---|---|
| Pilot campaigns | Test one territory with targeted offers (full-price, not deep-discount) | Orders and profit per territory |
| Copy the Southwest playbook | Reuse what works in the best-performing territories | Order growth vs Southwest |
| Local partnerships | Work with dealers or local events in these territories | New customers |

---

### Strategy 6: Diversify Beyond Bikes 🚲
**Insight:** Bikes make up roughly 85% of sales; Components are a distant second, and Clothing and Accessories are tiny.
**Goal:** Reduce concentration risk and lift order value through add-ons.

| Tactic | How | Metric to Track |
|---|---|---|
| Attach-rate programs | Offer accessories / clothing with every bike purchase | Accessory attach rate |
| Bundles | Complete riding kits (bike + helmet + gloves + jersey) | Revenue from non-bike categories |
| Long-tail rationalization | Review the many small subcategories in the TreeMap and drop or merge the ones that add cost without profit | Profit per SKU |

---

### Strategy 7: Inventory & Availability Control 📦
**Insight:** 98 products (33.22%) are out of stock.
**Goal:** Never run out of profitable products; stop stocking dead weight.

| Tactic | How | Metric to Track |
|---|---|---|
| Prioritize by profit | Restock Road Bikes, Mountain Bikes, Touring Bikes and frames first | Out-of-stock % among top products |
| ABC analysis | Classify products by sales and profit contribution and set service levels per class | Stock-out rate by class |
| Reorder points & alerts | Trigger replenishment automatically before stock reaches zero | Lost-sales incidents |
| Clear slow movers | Discontinue or bundle products with low profit and low sales | Inventory holding cost |

---

### Strategy 8: Customer Retention 🔁
**Insight:** There are about 1.65 orders per customer, while the Pacific region reaches about 1.9.
**Goal:** Turn one-time buyers into repeat customers.

| Tactic | How | Metric to Track |
|---|---|---|
| Replenishment reminders | Email customers when accessories, tires or clothing are due for replacement | Repeat purchase rate |
| Loyalty program | Reward repeat purchases with points, not price cuts | Orders per customer |
| Study the Pacific pattern | Understand why Pacific customers reorder more and apply it elsewhere | Orders per customer by region |

---

### Strategy 9: Data & Monitoring 📈
**Goal:** Make sure decisions are based on trustworthy numbers.

| Tactic | How |
|---|---|
| Verify the 2014 data range | Confirm whether the 2014 drop is a real decline or a partial year |
| Add margin KPIs to the dashboard | Profit % by region, category and discount band |
| Set alerts | Flag any region, product or discount band that falls below the target margin |
| Monthly review meeting | Review the dashboard with Sales, Finance and Inventory owners |

---

### 🗓️ Implementation Roadmap

| Phase | Timeframe | Focus | Strategies |
|---|---|---|---|
| **Phase 1: Quick Wins** | 0 – 30 days | Stop the bleeding with low-effort changes | Discount approval workflow, free-shipping threshold, verify 2014 data, restock top products |
| **Phase 2: Fix the Core** | 30 – 90 days | Attack the root causes | Regional loss analysis and pricing, bundles, volume-pricing redesign, segment profiling |
| **Phase 3: Grow Profitably** | 90 – 180 days | Scale what works | Expansion pilots, diversification programs, loyalty and retention |

### ⚖️ Priority Matrix

| Strategy | Impact | Effort | Priority |
|---|---|---|---|
| 1. Order Value Optimization | High | Low | 🥇 Start now |
| 2. Discount Governance | High | Low | 🥇 Start now |
| 3. Fix Loss-Making Regions | High | Medium | 🥈 Next |
| 4. Convert Low-Profit Segment | High | Medium | 🥈 Next |
| 7. Inventory Control | Medium | Medium | 🥈 Next |
| 6. Diversify Beyond Bikes | Medium | Medium | 🥉 Later |
| 8. Customer Retention | Medium | Medium | 🥉 Later |
| 5. Grow Under-Penetrated Territories | Medium | High | 🥉 After Strategies 1–3 |
| 9. Data & Monitoring | Enabler | Low | Run in parallel |

### 📊 Success KPIs to Track on the Dashboard

| KPI | Today | Direction |
|---|---|---|
| Profit Percentage | 3.38% | ⬆️ Increase |
| Total Loss (all regions) | ≈ $5.4M | ⬇️ Decrease |
| Share of orders ≤ $431 | measure in the data | ⬇️ Decrease |
| Value of discounts > 200 | $2.73M | ⬇️ Decrease without hurting volume |
| Out-of-stock products | 33.22% | ⬇️ Decrease |
| Orders per customer | ≈ 1.65 | ⬆️ Increase |
| Bikes share of sales | ≈ 85% | ⬇️ Gradually decrease |

> 📝 **Note:** Targets should be set by the business after the Phase 1 baseline is measured. The figures above are current values from the dashboard, and the directions are the recommended goals.

### ⚠️ Risks to Watch

| Risk | Mitigation |
|---|---|
| Higher minimum orders may reduce order count | Test in a few territories first and watch total profit, not order count |
| Lower discounts may reduce volume | Use A/B tests and cap discounts instead of removing them |
| Price increases may push customers to competitors | Raise prices only on consistently loss-making products |
| Small samples in some regions | Check the number of orders before acting on regional results |

---

## 🧰 Tools Used

- **Power BI Desktop**
- **Power Query:** data cleaning and preparation
- **DAX measures:** Total Real Sales · Real Profit · Loss · Profit % · Discounts > 200 · Number of Customers / Orders
- **Data Modeling:** relationships between Sales, Products, Customers, Territory and Date
- **AI Visuals:** Key Influencers · Top Segments · Decomposition Tree
- **Dashboard design:** custom theme, icons, slicers, navigation buttons

---

## 🚀 How to Use the Dashboard

1. Open `FinancialDashboard.pbix` in **Power BI Desktop**.
2. Use the slicers on the left (Month, Product Category, Region Group, ProductStatus) to filter the data.
3. Click **KeyInfluence**, **DecompositionTree** or **TreeMap** in the header to open a deep-dive page.
4. Click the **back arrow** to return to the main dashboard.
5. If you change the data: **Home → Refresh**.

---
⭐ If you like this dashboard, leave a star on the project!
