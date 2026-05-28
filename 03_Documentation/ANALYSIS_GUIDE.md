# Analysis Guide - COVID-19 Dashboards

## Purpose
Instructions for creating and updating the 5 main COVID-19 analysis dashboards.

---

## Dashboard 1: Temporal Trends & Volatility Analysis

### What It Shows
- **Top Left**: Quarterly pandemic rates (bars) by year
  - 2020-2022: High rates
  - 2023-2026: Declining trend
  
- **Top Right**: 3-month moving average trend (line)
  - Peak: ~220 cases in mid-2021
  - Current: Stabilized ~20 cases
  
- **Bottom Left**: Seasonal monthly patterns
  - Peaks: October-November every year
  - Valleys: Summer months (June-August)
  
- **Bottom Right**: Volatility over time (declining line)
  - 2020-2022: High volatility (140)
  - 2026: Low volatility (20)

### How to Create in Power BI

**Step 1: Data Setup**
```
1. Import Excel with columns: Year, Quarter, Month, Rate, Volatility
2. Create Date field from Year/Quarter
3. Ensure sort order: 2020→2026
```

**Step 2: Visualizations**
```
Visual 1 - Quarterly Bars:
- X-axis: Quarter
- Y-axis: Rate (if provided) or Cases
- Legend: Year (different colors)
- Filter: Last 6 years

Visual 2 - Trend Line:
- X-axis: Date (month)
- Y-axis: Moving Average (if have raw data)
- Format: Smooth line with area

Visual 3 - Monthly Pattern:
- X-axis: Month (01-12)
- Y-axis: Average Rate
- All years overlaid
- Use different colors per year

Visual 4 - Volatility Decline:
- X-axis: Year
- Y-axis: Volatility (std dev)
- Format: Line or column chart
```

**Step 3: Formatting**
```
- Color scheme: Green for declining, Red for peaks
- Title: "COVID-19 Temporal Trends & Volatility Analysis"
- Add text box explaining seasonal peaks
```

---

## Dashboard 2: Demographic Risk Analysis

### What It Shows
- **Left Side**: Average monthly rates by demographic
- **Center**: Peak monthly rates (table/heatmap)
  - Seniors 85+: 197 (highest)
  - Children 0-17: 22 (lowest)
- **Right Side**: Bar charts by race, age, gender
- **Heatmap**: Risk by race × age combinations

### How to Create in Power BI

**Step 1: Data Setup**
```
1. Import data with: Race_Clean, Age_Group, Sex, Rate, Deaths
2. Aggregate by demographic groups
3. Create Avg_Rate and Peak_Rate columns
```

**Step 2: Visualizations**

```
Visual 1 - Main KPI Cards:
- Avg Monthly Rate: 42.5
- Peak Monthly Rate: 207.64

Visual 2 - Demographic Heatmap:
- Rows: Race_Clean
- Columns: Age_Group
- Values: Avg monthly rate (dark = higher)
- Use color gradient green→yellow→red

Visual 3 - Highest States Bar Chart:
- X-axis: State
- Y-axis: Avg Monthly Rate
- Top 7 states: IA, CT, NY, NM, CA, CO, NY
- Sort descending

Visual 4 - Breakdown by Dimension:
- Three column charts:
  - By Race
  - By Age Group
  - By Gender

Visual 5 - Trend Over Time:
- X-axis: Year
- Y-axis: Rate filtered by demographic
- Interactive legend
```

### Analysis Insights
- **Disparities**: American Indian/Alaska Native populations have higher rates
- **Age Effect**: Strong correlation: older = higher risk
- **Gender**: Generally similar across genders
- **Geographic**: Iowa, Connecticut, New York show persistent high rates

---

## Dashboard 3: State Risk vs Volatility

### What It Shows
- Bubble chart with:
  - **X-axis**: Volatility (monthly std dev)
  - **Y-axis**: Average risk (mortality rate)
  - **Bubble Size**: Total cases
  - **Each bubble**: One state

### How to Create in Power BI

**Step 1: Data Prep**
```
Calculate for each state:
- Avg_Monthly_Rate (X-axis)
- Volatility (std dev of monthly) (Y-axis)  
- Case_Count (bubble size)
```

**Step 2: Visualization**
```
Visual: Scatter + Bubble Chart
- X Values: Avg Monthly Rate (0-80+)
- Y Values: Volatility (0-150+)
- Size: Case count
- Legend: State codes
- Add data labels for state names

Zones (optional):
- Low Risk, Low Volatility (green) - ideal
- High Risk, High Volatility (red) - concerning
- High Risk, Low Volatility (yellow) - stable but elevated
```

**Step 3: Interpretation**
```
Reading the chart:
- IA (Iowa): High volatility, moderate risk → unpredictable
- WA: Low volatility, low risk → stable and safe
- CT, NY: Cluster high risk, moderate volatility → persistent problem
- Most states: Converging toward low-volatility, low-risk zone
```

---

## Dashboard 4: Racial Risk vs Volatility

### Similar to Dashboard 3 but:
- X-axis: Avg Monthly Rate by race
- Y-axis: Demographic Volatility
- Bubble: Each racial group
- Shows equity disparities

**Key Finding**:
- American Indian/Alaska Native: Far upper right (high risk, high volatility)
- Asian/Pacific Islander: Lower left (lower risk)
- Shows persistent racial disparities regardless of trend

---

## Dashboard 5: Age Group Risk vs Volatility

### Similar structure:
- Each age group as bubble
- Seniors 85+: Extreme upper right (197 volatility!)
- Age 0-17: Lower left (safer, more stable)
- Shows age is strongest risk factor

---

## Common Excel Calculations

### Calculate Volatility in Excel
```excel
=STDEV(RangeOfMonthlyRates)

Example:
=STDEV(B2:B13)    # For 12 months
```

### Calculate 3-Month Moving Average
```excel
=AVERAGE(OFFSET(A1,0,0,3,1))

Or in Power BI/Excel:
=AVERAGE(PreviousMonth, CurrentMonth, NextMonth)
```

### Calculate Quarterly Average
```excel
=AVERAGEIFS(Rate_Column, 
            Quarter_Column,"Q1",
            Year_Column,2026)
```

### Calculate Peak Rate
```excel
=MAXIFS(Rate_Column, 
        Demographic_Column,"Senior 85+")
```

---

## Data Refresh Workflow

### Monthly Update Process
```
1. Download latest CDC/HHS data
2. Aggregate by: State, Race, Age, Gender, Month
3. Calculate: Avg_Monthly_Rate, Volatility
4. Save to: 01_Data/COVID_Data_June2026.xlsx
5. In Power BI:
   - Home → Refresh (if linked to Excel)
   - All dashboards update automatically
6. Take screenshots for export
7. Save in: 02_Dashboards/Images/
8. Update Excel reports with new data
```

### Quarterly Update
```
1. Recalculate quarterly aggregates
2. Update 3-year volatility rolling window
3. Review trending and outliers
4. Document key findings in 03_Documentation/
5. Commit to version control
```

---

## Dashboard Tips & Best Practices

### Visual Design
- Use consistent color: Green (improving) → Yellow (stable) → Red (concerning)
- Include year-over-year comparisons
- Show both absolute values and trends
- Add context boxes with key insights

### Interactivity (Power BI)
```
Add these slicers (filters):
- Year [2020, 2021, 2022, 2023, 2024, 2025, 2026]
- Race [All, White, Black, Hispanic, Asian, American Indian]
- Age Group [All age groups or specific ones]
- State [All, or top 10]
```

### Mobile Responsiveness
- Not all visuals fit small screens
- Create simplified "mobile" page if needed
- Test on tablets

### Export for Presentations
```
1. Screenshot dashboards (2560×1440 resolution)
2. Export as PNG/JPG
3. Save in: 02_Dashboards/Images/
4. Use in PowerPoint/presentations
```

---

## Troubleshooting

**Q: Dashboard won't refresh?**
A: Force refresh - Power BI Home → Refresh, or close/reopen

**Q: Missing data for some demographics?**
A: Common - not all combinations have data. Use filters to find available data.

**Q: Volatility calculation differs from CDC?**
A: Check if calculating from same date range. Use rolling 12-month window for consistency.

**Q: How to compare two years?**
A: Use slicer for Year, or create separate chart side-by-side for visual comparison.

---

## Resources

- [Power BI Desktop Docs](https://docs.microsoft.com/power-bi/)
- [DAX Functions](https://dax.guide/)
- [Excel Functions](https://support.microsoft.com/office/excel-functions)
