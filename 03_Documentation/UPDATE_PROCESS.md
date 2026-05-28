# Update Process - Keeping Data Current

## Quick Summary

When new data arrives, follow these 5 steps to update everything.

---

## Step 1: Add Data to 01_Data/

**Location**: `C:\laragon\www\covid_hospitalization_analysis\01_Data\`

**What to do**:
```
1. Download latest COVID data
2. Format in Excel with columns:
   - Date/Year/Quarter/Month
   - State
   - Race_Clean
   - Age_Group
   - Sex
   - Rate/Cases/Deaths fields
   
3. Save as: COVID_Data_YYYY-MM-DD.xlsx
   Example: COVID_Data_2026-06-27.xlsx
   
4. Keep old versions - don't overwrite!
   It's OK to have multiple files
```

---

## Step 2: Update Power BI Dashboards

**Location**: `02_Dashboards/PowerBI/`

**Process**:
```
1. Open Temporal_Trends_Analysis.pbix
2. Go to Home tab
3. Click Refresh
   (Waits for Excel to reload)
4. Check that visualizations updated
5. Save file

Repeat for other .pbix files:
- Demographic_Risk_Dashboard.pbix
- State_Risk_Volatility.pbix
(etc.)
```

**If using SQL Server connection**:
```
1. Instead of Refresh, use:
   Home → Get Data → (connection)
2. Re-import latest dataset
3. Update data mappings if columns changed
```

---

## Step 3: Create Excel Reports

**Location**: `02_Dashboards/Excel/`

**Process**:
```
1. Open last month's report:
   Weekly_Report_2026-05-20.xlsx

2. Copy data from 01_Data/COVID_Data_latest.xlsx
   
3. Create/update pivot tables:
   - Select new data range
   - Insert → Pivot Table
   
4. Update charts:
   - Right-click → Refresh
   
5. Save New Version:
   Weekly_Report_2026-06-27.xlsx
   (change date to today)
```

**What calculations to update**:
- AVERAGE() - average rates
- STDEV() - volatility calculations
- MAXIFS() - peak rates
- Trend formulas

---

## Step 4: Take Screenshots

**Location**: `02_Dashboards/Images/`

**Process**:
```
For each Power BI dashboard:

1. Open dashboard in Power BI Desktop
2. Set filters as desired
   (e.g., "Last 3 years")
   
3. Screenshot entire dashboard
   Windows key + Shift + S
   Select dashboard area
   
4. Save image as:
   Dashboard_Name_YYYY-MM-DD.png
   Example: Temporal_Trends_2026-06-27.png
   
5. Place in 02_Dashboards/Images/
```

**Tips**:
- Use full resolution (2560×1440 if possible)
- Include title and date
- Remove sensitive info if sharing externally

---

## Step 5: Update Documentation

**Location**: `03_Documentation/`

**Update these files if needed**:

### DATA_FIELDS.md
```
- Add any new columns to the table
- Update ranges/examples if different now
- Note last update date
```

### ANALYSIS_GUIDE.md
```
- Update "Last Updated" date
- Add new insights from latest data
- Note any changed interpretations
```

### Create CHANGELOG.md
```
2026-06-27:
- Added June data
- Volatility declining as expected
- New states showing higher rates
- Demographic disparity persists

2026-05-27:
- Initial dashboard creation
- [etc]
```

---

## Version Control (Git)

### Track your changes
```bash
# See what changed
git status

# Add new files
git add 01_Data/*.xlsx
git add 02_Dashboards/Images/*.png
git add 03_Documentation/*.md

# Commit with message
git commit -m "Update COVID data to June 27, 2026

- Added month of June data
- Volatility trending down
- All dashboards refreshed
- New demographic insights"

# Push to remote
git push origin main
```

### Good commit messages
```
✅ "Update COVID data to June 2026 - volatility declining"
❌ "update"
❌ "changes"
✅ "Add demographic analysis for 85+ age group showing 197 volatility"
❌ "Added stuff"
```

---

## Monthly Checklist

Use this every month:

- [ ] Download new data for latest month
- [ ] Place in 01_Data/
- [ ] Refresh all Power BI dashboards
- [ ] Verify visualizations look correct
- [ ] Update Excel pivot tables
- [ ] Calculate new volatility metrics
- [ ] Create dashboard screenshots
- [ ] Update CHANGELOG.md
- [ ] Update documentation if needed
- [ ] Git commit with date and changes
- [ ] Share screenshots with stakeholders

---

## Quarterly Checklist

Every 3 months do a deeper review:

- [ ] Review trend analysis from all 4 quarters
- [ ] Compare year-over-year patterns
- [ ] Document seasonal findings
- [ ] Update demographic disparity notes
- [ ] Recalculate 12-month volatility windows
- [ ] Create quarterly report
- [ ] Archive old screenshots

---

## Common Update Scenarios

### Scenario 1: New Month of Data
```
1. Add June data to Excel
2. Save as COVID_Data_2026-06-27.xlsx
3. Power BI → Refresh
4. Take new screenshots
5. Git commit
Done! (15 minutes)
```

### Scenario 2: New Demographic Category
```
1. Add new Race or Age group to data
2. Update DATA_FIELDS.md with new category
3. Power BI: Re-map data if needed
4. Add new dimension to dashboards if wanted
5. Git commit
Done! (30 minutes)
```

### Scenario 3: Correcting Historical Data
```
1. Replace old month's data
2. Recalculate all derived metrics (volatility, trends)
3. Power BI → Refresh
4. Update all dashboards
5. Take screenshots
6. Document correction in CHANGELOG.md
7. Git commit with explanation
Done! (1 hour)
```

---

## Troubleshooting Updates

**Q: Power BI won't refresh?**
```
1. Close Power BI completely
2. Close Excel file
3. Reopen both
4. Try Refresh again
5. If still fails, try: Home → Get Data (re-import fresh)
```

**Q: Excel charts look wrong after update?**
```
1. Right-click chart
2. Edit Data
3. Update range to new data
4. Click OK
5. Chart refreshes automatically
```

**Q: Old screenshots still in Images folder?**
```
You can:
- Keep all (good for archive)
- Move old to subfolder: Images/Archive/
- Delete only with confirmation
Don't lose important versions!
```

**Q: Forgot to update documentation?**
```
It's OK to catch up:
1. Add notes retroactively
2. Update CHANGELOG for past months
3. Commit with message: "Retroactive documentation update"
4. Next month do it on schedule
```

---

## Tips for Success

✅ **DO**:
- Update immediately when new data arrives
- Keep old files (version control)
- Document changes in commit messages
- Name files with dates
- Take screenshots regularly

❌ **DON'T**:
- Overwrite old Excel files
- Forget to commit changes
- Leave visualizations outdated
- Delete images/reports
- Work directly on original data

---

## When to Ask for Help

Get support if:
- Power BI won't open dashboard
- Excel formulas are broken
- Don't know how to calculate volatility
- Need to add new visualization
- Want to change dashboard design
- Data doesn't look right

Contact: analytics@hospital.com
Slack: #covid-analysis
