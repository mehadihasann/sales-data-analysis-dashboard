# Sales Data Analysis Dashboard

An end-to-end sales analytics case study: from raw retail data to executive-ready insights and an interactive Power BI dashboard. Built to answer one question - **which products, categories, regions, and customers actually drive revenue, and where should the business focus next?**

## Key findings

- **Volume-led growth** - Revenue grew 50% from 2015 to 2018 ($480k to $722k), driven by a 75% rise in order volume. Average order value slipped ($507 to $435): the business wins on reach, not ticket size.
- **The Office Supplies paradox** - 60% of all transactions but only 31% of revenue (small tickets, high volume). Yet it grows fastest at 17.1% CAGR - the hidden growth engine.
- **H2 carries the year** - November runs at 186% of an average month; Q4 delivers ~39% of annual revenue, every year. February sits at just 32%.
- **Fiercely loyal base, no acquisition** - 98% of customers are repeat buyers driving 99.8% of revenue. Retention is solved; new-customer growth is the gap.
- **Geography is the concentration risk** - California + New York = one third of all revenue. Products are well diversified (top 10 = 10.8%); states are not.
- **Operations is a quiet strength** - fulfilment forms a clean ladder (Same Day 0.04 days to Standard 5.0) and no ship mode ever breaches its promise window.

## Recommendations (from the analysis)

1. Fund the H2 surge - shift inventory, staffing, and marketing toward Sep-Dec instead of a flat annual plan.
2. Invest behind Office Supplies - small lifts in ticket or attachment rate compound fast at 17% CAGR.
3. Fix acquisition - build a new-customer program; the base is loyal but static.
4. De-risk CA + NY - replicate what works there in Texas and Washington next.
5. Protect the East's ticket premium ($489 AOV vs $426 Central) before pushing volume plays.

Full reasoning, code, and charts: [`sales-dashboard-project/notebook/analysis.ipynb`](sales-dashboard-project/notebook/analysis.ipynb)

## Analysis charts

All eight charts render inline in the notebook - open [`sales-dashboard-project/notebook/analysis.ipynb`](sales-dashboard-project/notebook/analysis.ipynb) to see them alongside the code that produced them:

- Yearly revenue and order growth (dual axis)
- Category revenue mix (donut) and category CAGR bars
- Monthly seasonality index
- Top 10 sub-categories and top 10 states
- Fulfilment time by ship mode
- Regional revenue and average order value

## Dashboard previews (Power BI)

<img width="908" alt="Sales overview dashboard" src="https://github.com/user-attachments/assets/b75bbf10-9be9-42cb-92e6-f2a19f9a814f" />
<img width="868" alt="Regional performance view" src="https://github.com/user-attachments/assets/34fd7bcd-48ab-4308-9a56-4e917a512a88" />
<img width="1212" alt="Category breakdown" src="https://github.com/user-attachments/assets/6a2ab85b-e576-44f8-b256-ad83c2d98e58" />
<img width="638" alt="Product performance view" src="https://github.com/user-attachments/assets/e98df564-1d11-4ce6-99f6-ee445b855c93" />

## Methodology

1. **Audit** - missing values, duplicates, date parsing, grain check (11 missing postal codes, 0 duplicates, clean 2015-2018 range).
2. **Explore** - revenue, orders, and AOV trends; category/segment/region mix; seasonality index; customer loyalty and concentration; fulfilment times.
3. **Recommend** - findings ranked by expected business impact, each traceable to a computed result.

## Project structure

```
sales-dashboard-project/
  data/
    train.csv            # 9,800 retail order lines, 2015-2018
    DATA_DICTIONARY.md   # column definitions
  notebook/
    analysis.ipynb       # full analysis: narrative, code, charts (23 cells)
  images/                # exported charts
requirements.txt         # Python dependencies
```

## How to run

```bash
pip install -r requirements.txt
cd sales-dashboard-project/notebook
jupyter notebook analysis.ipynb
```

## Tools

Python (pandas, matplotlib, numpy) · Power BI · Jupyter

## Limitations

- No profit, discount, or quantity fields in the source data, so margin analysis was out of scope.
- No returns data; customer analysis is order-count based (a full RFM segmentation is the natural next step).
- Figures are nominal USD, 2015-2018, for a single retailer.
