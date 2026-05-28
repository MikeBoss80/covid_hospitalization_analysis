# Quick Start - Getting Your Dashboards Running in 10 Minutes

## 📋 Prerequisites (Already Have?)
- [ ] Excel with your COVID data
- [ ] Power BI Desktop (free download from Microsoft)
- [ ] Your project files downloaded

---

## ⚡ 5-Minute Setup

### Step 1: Put Your Data in the Right Place (1 min)

```
Your Excel file should go here:
C:\laragon\www\covid_hospitalization_analysis\01_Data\

Recommended filename:
COVID_Data_2026-05-27.xlsx

(Replace date with today's date)
```

### Step 2: Open Power BI Desktop (1 min)

```
1. Download Power BI Desktop (free)
   → powerbi.microsoft.com/desktop
   
2. Click "Open"
3. You should see empty canvas
```

### Step 3: Connect to Your Excel Data (2 min)

```
In Power BI:

1. Home → Get Data
2. Select "Excel Workbook"
3. Navigate to: C:\laragon\www\covid_hospitalization_analysis\01_Data\
4. Select your COVID_Data file
5. Click Load
6. Select the sheet with your data
7. Click Load again

You should now see your data in the "Fields" pane on right ✓
```

### Step 4: Create First Visualization (1 min)

```
1. Visualizations panel → Select "Line Chart"
2. Drag fields to chart:
   - "Date" → X-axis
   - "Rate" → Y-axis
3. See your first chart appear!
```

---

## 📊 Create Your 5 Dashboards

Copy this structure 5 times (once per dashboard):

### Dashboard 1: Temporal Trends
**Files to create**:
- `02_Dashboards/PowerBI/Temporal_Trends_Analysis.pbix`

**Visualizations needed**:
1. Quarterly bars (by year)
2. Trend line (3-month moving average)
3. Monthly seasonal pattern
4. Volatility over time

**Data fields**:
- Year, Quarter, Month, Date
- Rate, Volatility

---

### Dashboard 2: Demographic Risk
**Files**:
- `02_Dashboards/PowerBI/Demographic_Risk_Dashboard.pbix`

**Visualizations**:
1. KPI cards (avg rate, peak rate)
2. Heatmap (race × age)
3. Bar chart (by race)
4. Bar chart (by age)
5. Bar chart (by gender)

**Data fields**:
- Race_Clean, Age_Group, Sex
- Rate, Deaths

---

### Dashboard 3: State Risk vs Volatility
**Files**:
- `02_Dashboards/PowerBI/State_Risk_Volatility.pbix`

**Visualizations**:
1. Bubble chart (scatter with size)
   - X: Avg rate per state
   - Y: Volatility per state
   - Size: Number of cases
   - Labels: State codes

**Data fields**:
- State, Rate, Volatility, Case_Count

---

### Dashboard 4: Racial Risk vs Volatility
**Files**:
- `02_Dashboards/PowerBI/Racial_Risk_Volatility.pbix`

**Visualization**:
1. Bubble chart (similar to #3)
   - X: Rate by race
   - Y: Volatility by race

**Data fields**:
- Race_Clean, Rate, Volatility

---

### Dashboard 5: Age Group Risk vs Volatility
**Files**:
- `02_Dashboards/PowerBI/Age_Group_Risk_Volatility.pbix`

**Visualization**:
1. Bubble chart
   - X: Rate by age group
   - Y: Volatility by age group

**Data fields**:
- Age_Group, Rate, Volatility

---

## 💾 Save Your Dashboards

When creating each dashboard:

```
File → Save
Location: C:\laragon\www\covid_hospitalization_analysis\02_Dashboards\PowerBI\
Filename: [Dashboard_Name].pbix
```

---

## 📈 Create Excel Reports

### Step 1: Copy Data to Excel
```
1. Open your COVID_Data_2026-05-27.xlsx
2. Keep the main data sheet
3. Add new sheet: "Pivot_Data"
```

### Step 2: Create Pivot Table
```
1. Select your data
2. Insert → Pivot Table
3. Drag fields to areas:
   - Rows: Race, Age, State
   - Values: Count of records
```

### Step 3: Create Charts from Pivot
```
1. Select pivot table
2. Insert → Charts (Bar, Line, etc)
3. Arrange on sheet
4. Save as: Weekly_Report_2026-05-27.xlsx
   in 02_Dashboards/Excel/
```

---

## 📸 Take Screenshots

For each dashboard:

```
1. Open in Power BI
2. Press: Windows Key + Shift + S
3. Select entire dashboard area
4. Name: [Dashboard_Name]_2026-05-27.png
5. Save in: 02_Dashboards/Images/
```

---

## 📝 Document Your Work

Edit these files:

### 1. UPDATE_PROCESS.md
```
Already has the instructions
Each month, follow those steps
```

### 2. CHANGELOG.md
```
1. Open file
2. Add section at top with today's date
3. List what you added/changed
```

### 3. DATA_FIELDS.md
```
1. List every column in your Excel
2. Describe what it means
3. Give example values
```

---

## ✅ You're Done!

Now you have:
- ✅ 5 Power BI dashboards
- ✅ Excel reports with analysis
- ✅ Screenshots for presentations
- ✅ Documented your work

### What's Next?

**Monthly Workflow:**
```
1. New data arrives
2. Update Excel file in 01_Data/
3. Power BI → Refresh
4. Excel → Update pivot tables
5. Take new screenshots
6. Update CHANGELOG.md
7. Git commit
Done! (15-30 minutes)
```

---

## 🆘 Something Wrong?

**Power BI won't open?**
- Close and reopen
- Reinstall if needed (free download)

**Can't find your data?**
- Make sure Excel is in `01_Data/`
- Check filename is correct
- Verify Excel file has data (not blank)

**Visualizations blank?**
- Check fields are assigned
- Verify data has values (not null)
- Try different chart type

**Need help?**
- See `03_Documentation/ANALYSIS_GUIDE.md` for detailed examples
- Check `README.md` for overview
- Email: [your support]

---

## 🎯 Final Checklist

- [ ] Data file in `01_Data/COVID_Data_[DATE].xlsx`
- [ ] All 5 dashboards created in `02_Dashboards/PowerBI/`
- [ ] Excel report saved in `02_Dashboards/Excel/`
- [ ] Screenshots taken to `02_Dashboards/Images/`
- [ ] Documentation updated
- [ ] Files committed to Git
- [ ] Everything looks correct

**Congratulations! Your COVID analysis project is live! 🎉**

---

**Time to complete**: ~45 minutes total
**Frequency**: Update monthly with new data

For detailed instructions, see [ANALYSIS_GUIDE.md](ANALYSIS_GUIDE.md)
