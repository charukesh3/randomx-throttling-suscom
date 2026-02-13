# Dataset: merged_5min.csv

This folder contains the **5-minute merged table** used for the paper.

## File
- `merged_5min.csv`: one row per 5-minute interval.

## Columns (observed)
decision_time_ist, difficulty_used, diff_ratio, state_final, power_w_avg, temp_c_avg, hashrate_hs_avg, kWh_5min, cost_5min, hashes_5min, hash_per_kWh, hash_per_J, tariff_inr_per_kwh, state_change, hash_per_kwh_5min

## Units
- `decision_time_ist`: timestamp (IST)
- `power_w_avg`: wall power in watts (W), averaged over the 5-minute interval
- `hashrate_hs_avg`: hashrate in hashes/second (H/s), averaged over the 5-minute interval
- `kWh_5min`: energy in kWh consumed during the 5-minute interval
- `hashes_5min`: hashes computed during the 5-minute interval
- `cost_5min`: cost (INR) for the 5-minute interval using `tariff_inr_per_kwh`

## Notes
- The current exported sheet does **not** include `R_k` (normalized difficulty ratio). If you want the plots that depend on `R_k`, add a column named `R_k` in the Merged sheet (or export it into the CSV) and rerun the plotting script.
