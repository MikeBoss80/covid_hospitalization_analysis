# Data Fields Guide - COVID-19 Analysis

## Dataset Overview
COVID-19 hospitalization, mortality, and demographic data from 2020-2026 covering US states and demographic groups.

---

## Core Dimensions

### Time Dimension
| Field | Type | Description | Example |
|-------|------|-------------|---------|
| **Year** | Integer | Calendar year | 2020, 2021, ..., 2026 |
| **Quarter** | String | Quarter (Q1-Q4) | Q1, Q2, Q3, Q4 |
| **Month** | String | Month name | January, February, ... |
| **Month_Number** | Integer | Month number | 1-12 |
| **Date** | Date | Specific date | 2026-05-27 |

### Geographic Dimension
| Field | Type | Description | Example |
|-------|------|-------------|---------|
| **State** | String | US State code | CA, NY, TX, IA |
| **State_Name** | String | Full state name | California, New York |
| **Region** | String | Geographic region | Northeast, South, Midwest, West |

### Demographic Dimension
| Field | Type | Description | Valid Values |
|-------|------|-------------|---------------|
| **Race** | String | Racial/ethnic category | White, Black, Hispanic, Asian/Pacific Islander, American Indian/Alaska Native |
| **Race_Clean** | String | Categorized race | White, Black, Hispanic, Asian/Pacific Islander, American Indian/Alaska Native, All Races |
| **Age_Group** | String | Age bracket | Children (0-17), Adults (18+), Adults (18-49), Adults (30-39), Adults (40-49), Seniors (65+), Seniors (65-74), Seniors (75-84), Seniors (85+) |
| **Sex** | String | Gender | Male, Female, Added (unknown/other) |

### Metrics Dimension
| Field | Type | Description | Range |
|-------|------|-------------|-------|
| **Avg_Monthly_Rate** | Float | Average monthly death rate | 0-200+ |
| **Monthly_Volatility** | Float | Volatility (standard deviation) | 0-150+ |
| **Peak_Monthly_Rate** | Float | Highest monthly rate recorded | Variable |
| **Cases** | Integer | Number of cases | 0+ |
| **Deaths** | Integer | Number of deaths | 0+ |
| **Mortality_Rate** | Float | Deaths per unit population | 0-100+ |

---

## Used in Dashboards

### Dashboard 1: Temporal Trends & Volatility
**Fields Used**:
- Year, Quarter, Month, Date
- Avg_Monthly_Rate
- Monthly_Volatility (for trend lines)
- Demonstrates: Peaks in 2021-2022, seasonal patterns (Oct-Nov), declining volatility 2023-2026

### Dashboard 2: Demographic Risk Analysis
**Fields Used**:
- Race_Clean, Age_Group, Sex
- Peak_Monthly_Rate
- Avg_Monthly_Rate
- Shows: 
  - Seniors (85+): highest rates (~195)
  - American Indian/Alaska Native: highest disparity
  - Geographic variation (IA, CT, NY highest)

### Dashboard 3: State Risk vs Volatility
**Fields Used**:
- State, Avg_Monthly_Rate, Monthly_Volatility
- Scatter plot with bubbles
- Shows: IA (high volatility), WA (low), CT/NY (high risk clusters)

### Dashboard 4: Racial Risk vs Volatility
**Fields Used**:
- Race_Clean
- Monthly_Volatility (Y-axis)
- Avg_Monthly_Rate (X-axis)

### Dashboard 5: Age Group Risk vs Volatility
**Fields Used**:
- Age_Group
- Monthly_Volatility (Y-axis)
- Avg_Monthly_Rate (X-axis)
- Shows: Seniors 85+ with highest volatility and rate

---

## Data Quality Notes

### Null Handling
- Empty cells = no data for that combination
- Not all states have data for all demographics
- Race data less complete than age/gender

### Calculations
- **Monthly_Volatility** = Standard deviation of monthly rates over period
- **Moving_Average_3M** = Average of current + 2 prior months
- **Peak_Monthly_Rate** = Maximum single month value in dataset

### Filters Applied
- Only COVID-confirmed cases (where applicable)
- Excludes "Unknown" race (use "All Races" for totals)
- Adult categories: 18+, 30-39, 40-49 represent specific sub-groups

---

## Data Updates

| Source | Frequency | Last Update |
|--------|-----------|-------------|
| CDC/HHS Database | Weekly | 2026-05-27 |
| State Health Depts | Varies | Varies |
| Mortality datasets | Monthly | 2026-05-27 |

---

## How to Add New Data

1. **New month arrived?**
   - Add row with Year, Quarter, Month, all states
   - Calculate Volatility
   - Update Peak_Monthly_Rate if needed

2. **New demographic?**
   - Add Race_Clean value to master list
   - Document in this file
   - Update all dashboards

3. **New state?**
   - Add rows for all demographic combinations
   - Ensure year/quarter fields populated
   - Use State_Name lookup for consistency
