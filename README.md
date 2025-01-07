# 2025 Goal Dashboard - 5K training
<img src="https://github.com/karammulc/2025-Goal-Dashboard/blob/main/Images/Goal%20Dashboard%20Logo.png" width="25%" alt="Goal Dashboard Logo">

After conquering my first cartwheel in 2024, I was ready for a new challenge. Enter 2025, when my best friend Camila proposed an exciting goal - completing a 5K together, along with a few other personal milestones.

## The Project

This challenge inspired me to create a comprehensive 5K Resolution tracking dashboard. While I typically rely on calculated fields, I expanded my practiced other elements of my toolkit by exploring new Google Sheets formulas. This approach allows for easier updates and centralized data management.

The dashboard is designed for Camila and I - for both encouragement and competition. 

# Dynamic Date-Based Formulas in Goal Dashboard

One of the most interesting aspects of this project was working with dynamic data that changed based on the current date and training week requirements. I developed two parallel sets of formulas - one for Camila and one for Kara - to track our individual progress.

## Core Dynamic Formulas

| Metric | Formula | Purpose |
|--------|---------|---------|
| Today's Week Number | `=IFERROR(INDEX(A:A, MATCH(1, (TODAY()>=C:C)*(TODAY()<=D:D), 0)), "No current week")` | Identifies the current training week based on today's date |
| Today's Mile Goal | `=IFERROR(INDEX(B:B, MATCH(1, (TODAY()>=C:C)*(TODAY()<=D:D), 0)), "No current week")` | Returns the mileage goal for the current week |
| Current End Date | `=IFERROR(INDEX(D:D, MATCH(1, (TODAY()>=C:C)*(TODAY()<=D:D), 0)), "No current week")` | Shows when the current training week ends |
| Remaining Days | `=IFERROR(INDEX(D:D, MATCH(1, (TODAY()>=C:C)*(TODAY()<=D:D), 0)) - TODAY(), "No current week")` | Calculates days left in current week |
| Current Week Mile Count | `=IFERROR(INDEX(E:E, MATCH(1, (TODAY()>=C:C)*(TODAY()<=D:D), 0)), "No current week")` | Tracks miles completed in current week |
| Weekly Progress | `=IFERROR(INDEX(H:H, MATCH(1, (TODAY()>=C:C)*(TODAY()<=D:D), 0)), "No current week")` | Shows percentage of weekly goal completed |
| Successful Weeks Count | `=ARRAYFORMULA(SUM(IF(H2:H100 >= 100%, 1, 0)))` | Counts weeks where 100% or more of goal was achieved |

- Each formula includes error handling to display "No current week" when outside training dates
- Uses INDEX MATCH combination for dynamic date based lookups
- ARRAYFORMULA for efficient calculation of successful weeks
- All formulas are duplicated and modified for both participants' tracking
Note: This documentation covers one set of formulas. An identical set exists with modified column references for tracking the other participant's progress.
## Dashboard Features

<img src="https://github.com/karammulc/2025-Goal-Dashboard/blob/main/Images/Goal%20Dashboard%20-%201.png" width="70%" alt="Goal Dashboard Top">
<img src="https://github.com/karammulc/2025-Goal-Dashboard/blob/main/Images/Goal%20Dash%20-%202.png" width="70%" alt="Goal Dashboard Bottom">

### Training Progress Tracking
- Current training week indicator
- Remaining days counter
- Weekly mileage tracking
- Goal completion percentage
- Total training progress

### Visual Analytics
- Dual-line progress chart (Kara & Camila)
- Day of week mileage distribution
- Resolution completion counter

### Data Management
<img src="https://github.com/karammulc/2025-Goal-Dashboard/blob/main/Images/Daily%20Log.png" width="70%" alt="Daily Log">
<img src="https://github.com/karammulc/2025-Goal-Dashboard/blob/main/Images/Weekly%20Summary.png" width="70%" alt="Weekly Summary">
<img src="https://github.com/karammulc/2025-Goal-Dashboard/blob/main/Images/Resolutions.png" width="70%" alt="Resolutions">

The system includes dedicated sheets for:
- Resolution logging
- Daily mileage tracking
- Weekly distance summaries
- Book progress tracking

🏃‍♀️**Status: Project in Progress** 🏃‍♀️

Next steps:

- Count of Successful Weeks - Formula complete, add to viz
- Weekly end date display - Formula complete, add to viz
- Customizable timespan views
- Dynamic milestone notifications
- % of weeks being successful : change to not include current week


