# Canada Innovation Compass

**Where should Canada invest in innovation? A Big Data look at regional business capacity and the shifting face of business R&D.**

Suggested repository name: `canada-innovation-compass`

Course project for ITM 760 (Assignment 2), using open Statistics Canada data and Python.

## Overview

Governments, lenders, and investors have limited capital for innovation and must decide where (which regions) and in what (which industries) to place it. This project explores three Statistics Canada tables to answer:

1. **Where?** How concentrated is Canada's employer-business base, and which regions specialise in innovation-adjacent sectors?
2. **Which sectors, and which way?** How has the number of R&D-performing businesses changed by industry from 2014 to 2023?
3. **Who spends how much?** How does average in-house R&D spending differ between Canadian-controlled and foreign-controlled firms?
4. **So what?** Which Big Data approaches would turn these descriptive signals into investment guidance?

The analysis is descriptive and does not establish causation. The business-count data are a single July 2024 snapshot and the R&D tables are Canada-wide, so province-level R&D comparisons are out of scope.

## Datasets

All three are from Statistics Canada. Download the CSV for each and place the files in the same folder as the notebook, using the file names below.

| File | Table | Measures | Grain and period |
|---|---|---|---|
| `33100766.csv` | [33-10-0766-01](https://www150.statcan.gc.ca/t1/tbl1/en/tv.action?pid=3310076601) Canadian Business Counts | Active businesses by NAICS and employment size | Census subdivision, July 2024 |
| `27100049.csv` | [27-10-0049-01](https://www150.statcan.gc.ca/t1/tbl1/en/tv.action?pid=2710004901) Business enterprise R&D performers by NAICS | Number of businesses reporting R&D | Canada, annual 2014-2023 |
| `27100355.csv` | [27-10-0355-01](https://www150.statcan.gc.ca/t1/tbl1/en/tv.action?pid=2710035501) Average in-house R&D expenditures | Average R&D spend per performer, by country of control | Canada, annual 2014-2023 |

The data are not included in this repository. Check Statistics Canada's open licence terms before redistributing them.

## What the notebook does

- Frames the problem and maps stakeholders to the decisions they face.
- Applies the 4Vs (Volume, Velocity, Variety, Veracity) to the data, with a measured data profile.
- Produces six figures with interpretations:
  1. Average R&D expenditure by country of control
  2. Employer businesses by province/territory
  3. Sector density per 1,000 businesses
  4. R&D performers by industry, 2014-2023
  5. Location-quotient heatmap, plus a k-means clustering of regions (demonstration)
  6. Indexed R&D trends (2014 = 100) with a naive linear projection to 2026
- Proposes Big Data approaches (clustering, hierarchical time-series forecasting, difference-in-differences, concentration metrics, record linkage).
- Translates findings into actions and metrics for Canadian economic development.

## Key findings

- **Concentration:** Ontario holds about 38% of employer businesses; Ontario, Quebec, and British Columbia together about 74%.
- **Manufacturing erosion:** R&D-performing manufacturers fell from 6,713 to 4,776 (-29%) between 2014 and 2023.
- **Services and health momentum:** Professional, scientific and technical services rose 25% (peaking in 2022), and health care and social assistance rose 108% from a small base.
- **Scale-up gap:** Foreign-controlled R&D performers spend roughly 8.4 times more per firm than Canadian-controlled ones, and the ratio has barely moved since 2014.

Figures are counts of firms and averages per performer, not total R&D dollars.

## How to run

```bash
git clone https://github.com/<your-username>/canada-innovation-compass.git
cd canada-innovation-compass
pip install pandas numpy matplotlib seaborn scikit-learn jupyter
jupyter notebook ITM760-Assignment2-improved.ipynb
```

Then place the three CSV files in the same folder and choose **Run All**. The notebook searches for the files by name below the working directory, so it must be started from the project folder.

## Limitations

- No provincial R&D data, so regional and R&D patterns cannot be correlated.
- The business-count data are a single snapshot and measure the stock of businesses, not startup births.
- No trade data were supplied.
- The scalar factor for table 27-10-0355-01 conflicts with a metadata note, so values are shown as published without rescaling.
- The clustering (13 regions) and the forecast (a straight-line trend on 10 points) are prototypes, not results to act on.

## Repository contents

```
Canada R&D Analytics.ipynb   Analysis notebook
README.md                           This file
```

## Author

Bang Nguyen
