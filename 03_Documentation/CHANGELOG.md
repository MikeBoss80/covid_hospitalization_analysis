# Changelog - COVID-19 Analysis Project

All notable changes to this project will be documented in this file.

---

## [2026-05-27] - Initial Setup

### Added
- Project structure with simplified architecture
- Power BI dashboards:
  - Temporal Trends & Volatility Analysis
  - Demographic Risk Analysis Dashboard
  - State Risk vs Volatility Analysis
  - Racial Risk vs Volatility Analysis
  - Age Group Risk vs Volatility Analysis
- Excel reports for static analysis
- Documentation:
  - Data Fields Guide
  - Analysis Guide with dashboard instructions
  - Update Process workflow
- Supporting files in version control

### Documentation
- Created DATA_FIELDS.md with all field descriptions
- Created ANALYSIS_GUIDE.md with dashboard creation steps
- Created UPDATE_PROCESS.md with monthly workflow
- Created FILES_CHECKLIST.md with file organization guide

### Current Insights
- Peak mortality rates occurred in 2021-2022
- Strong seasonal pattern: October-November peaks
- Volatility declining significantly 2023-2026
- Persistent demographic disparities by race and age
- Seniors 85+ show highest risk and volatility
- American Indian/Alaska Native populations have elevated rates
- Certain states (IA, CT, NY) show persistently high rates

---

## [TEMPLATE - Copy for new months]

## [YYYY-MM-DD] - Monthly Update

### Data Updated
- Added [Month] data
- Data through [Date]
- Row count: [##] total records

### Key Changes
- Volatility trend: [increasing/decreasing/stable]
- New peak observed: [if any]
- Demographic changes: [if any]

### Dashboards Updated
- Temporal Trends: Latest quarter added
- Demographic heatmap: Refreshed
- State risk bubbles: New positions

### Files Changed
- 01_Data/COVID_Data_[DATE].xlsx
- 02_Dashboards/PowerBI/*.pbix (Refreshed)
- 02_Dashboards/Excel/*.xlsx (Updated)
- 02_Dashboards/Images/*.png (New screenshots)

### Insights Noted
- [Key finding 1]
- [Key finding 2]
- [Disparity noted]

### Git Commit
```
Update COVID analysis to [Month] [Year]
- Added [Month] data
- Volatility: [trend]
- All dashboards refreshed
- [key insight]
```

---

## Version Control Notes

### How to Use This File

Each time you update your project with new data, add a section at the top (most recent first):

```
Format: [YYYY-MM-DD] - Brief Description

### Added
- What new things were created

### Changed
- What was modified

### Data Updated
- Row counts, date ranges

### Key Insights
- What you discovered

### Files Changed
- Which files were modified
```

### Commit Message Format

When you commit, summarize the change:

```bash
git commit -m "Update COVID data to June 2026

- Added June data (500 new records)
- Volatility declining as expected
- Demographic disparity in seniors persists
- Three states entering concerning zone"
```

---

## Tracking Updates

### Monthly Tasks Completed
- [x] May 27: Initial project setup
- [ ] June ??: June data added
- [ ] July ??: July data added
- etc.

### Quarterly Reviews
- [x] Q2 2026: Setup complete, dashboards functional
- [ ] Q3 2026: Mid-year review
- [ ] Q4 2026: Annual summary

### Annual Archives
- 2026: Initial year
- 2025: Historical (if retroactively added)
- 2024: Historical
- etc.

---

## Version Numbering

- **v1.0** - Initial project setup (May 2026)
- **v1.1** - First monthly update (June 2026)
- **v1.2** - Second monthly update (July 2026)
- etc.

Increment:
- Major (v2.0): Significant structure change, new dashboards, new data source
- Minor (v1.1): Monthly data updates, documentation improvements
- Patch (v1.1.1): Bug fixes, typos, small adjustments

---

## How Dashboards Evolved

### May 27, 2026
- Created all 5 dashboards based on provided specifications
- Connected to initial COVID dataset
- Established visualization patterns

### [Next updates]
- [When new analysis added]
- [When new demographic added]
- [When new state added]

---

## Data Quality Notes

### Data Issues Encountered
- None yet (add as you discover)

### Data Corrections Made
- None yet (add as you make corrections)

### Known Limitations
- Not all demographic combinations have data for all states
- Racial data less complete than age/gender
- Peak rates in 2021-2022 may reflect reporting changes rather than true peak

---

## Team Notes

### Contributors
- Primary Analyst: [Your name]
- Reviewer: [If applicable]

### Access
- Power BI: [Share link if published]
- Excel: Available in 02_Dashboards/Excel/
- Images: For presentations in 02_Dashboards/Images/

---

## Next Steps / TODO

- [ ] Get latest June 2026 data
- [ ] Add new age category if available
- [ ] Create summary report for stakeholders
- [ ] Archive May screenshots
- [ ] Update documentation
