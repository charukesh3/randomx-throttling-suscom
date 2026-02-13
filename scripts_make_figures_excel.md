# Figure generation (Excel-only)

If you prefer to generate the plots inside Excel (Office 365):

## 1) State over time
1. Select `decision_time_ist` and `state_final`.
2. Insert → Line chart.
3. Convert `state_final` to numeric helper column:
   - FULL=1, HALF=0.5, OFF=0
   - Insert a step chart by duplicating timestamps (optional) or keep a standard line.

## 2) Power time series
1. Select `decision_time_ist` and `power_w_avg`.
2. Insert → Line chart.
3. Format axis dates as `yyyy-mm-dd` and rotate labels.

## 3) Hashrate time series
1. Select `decision_time_ist` and `hashrate_hs_avg`.
2. Insert → Line chart.

## 4) Efficiency distribution by state
1. Create a new column: `hash_per_kwh_5min = hashes_5min / kWh_5min`.
2. Insert → PivotTable:
   - Rows: `state_final`
   - Values: `hash_per_kwh_5min` (set to Average)
3. For boxplot:
   - Filter to FULL and HALF, then Insert → Statistical chart → Box & Whisker.

## 5) Dwell time (state residence)
1. Create a column that flags a change:
   - `=IF(D2<>D1,1,0)` where D is `state_final`.
2. Compute run lengths (or use Power Query "Group By" on state runs).
3. Plot histogram of dwell times.
