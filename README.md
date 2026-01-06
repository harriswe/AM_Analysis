# AM_Analysis
Client Trading Risk & Performance Analysis

This repository contains a technical assessment of client trading behavior, focusing on position tracking, P/L attribution, and behavioral risk metrics (Toxicity and Holding Times).

🚀 Dashboard
[View the Live Analysis & Visualizations on DeepNote Note](https://deepnote.com/app/explorations-e439/AdvancedMarkets-ca4e7556-7ab0-4f97-a005-0c4324247595?utm_source=app-settings&utm_medium=product-shared-content&utm_campaign=data-app&utm_content=ca4e7556-7ab0-4f97-a005-0c4324247595)
: This interactive environment contains the visualizations.

🛠️ Project Components
1. Python Analysis (Analysis.ipynb)

The core code of the project. It handles the "heavy lifting" of data engineering, including:

    Data Sanitization: Cleaning malformed strings (e.g., handling dash-placeholders and comma-separators in financial values).

    Temporal Grouping: Using pd.Grouper and custom date-normalization to aggregate data into Daily, Weekly, and Monthly grains without losing raw trade precision.

    Cumulative Logic: Calculating running totals for both Position (Inventory) and P/L (Performance) across multiple instruments.

    Toxicity Detection: Identifying "Quick Turns" (flips within < 60 seconds) to flag potential scalping or high-frequency behavior.

2. Final Report (Trading_Analysis_Report.xlsx)

A multi-tabbed Excel workbook with the results (warning - not battle tested):

    All_Trade_Detail: The "Golden Source" file containing the original trade data appended with calculated risk metrics, as well as several additional columns of data derived from the original - used in calculations.

    Monthly_Summary: Monthly grain CP, and CPL data.

    Weekly_Summary: Weekly grain CP, and CPL data.

    Daily_Summary: Daily P/L data.

⚙️ Requirements & Usage

To run the notebook locally:

    Clone the repo.

    Ensure you have the following libraries: pandas, openpyxl, matplotlib.

    Run jupyter notebook Analysis.ipynb.

Why I Chose This Structure:

    Separation of Concerns: The code is for the developers; the Excel is for the managers; the DeepNote link is for the presentation.

    Scalability: The logic is written in Pandas (Python) to ensure it can handle datasets far larger than what Excel can process.

    Auditability: Every calculation in the summary tabs can be traced back to the All_Trade_Detail sheet.
