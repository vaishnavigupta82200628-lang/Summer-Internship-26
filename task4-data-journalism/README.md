# Task 4: Data Journalism Project — India's Groundwater Levels

## Status: Completed

## About
This project analyzes groundwater level data from the Atal Bhujal Yojana scheme
(2015–2022) across 7 Indian states — Gujarat, Haryana, Karnataka, Madhya Pradesh,
Maharashtra, Rajasthan, and Uttar Pradesh.

**Dataset source:** [data.gov.in — Ground Water Level Data under Atal Bhujal Yojana](https://www.data.gov.in/resource/disclosed-ground-water-level-data-under-atal-bhujal-yojana-2015-2022)

**Full analysis:** [Groundwater_Analysis.ipynb](./Groundwater_Analysis.ipynb)

## Key Findings

**1. National groundwater is declining overall**
India's average pre-monsoon groundwater depth went from ~20.1m in 2015 to ~21.2m
in 2022, meaning the water table dropped further underground. 2019 saw the sharpest
decline (22.6m).

**2. Rajasthan and Gujarat are the most stressed states**
Gujarat's pre-monsoon depth stayed consistently high (32–35m) across all 8 years.
Rajasthan saw the steepest decline of any state — from 19.8m in 2015 to 29.7m in
2022, a drop of nearly 10 metres.

**3. Karnataka showed a sudden improvement in 2022**
After staying in the 26–33m range from 2015–2021, Karnataka's depth improved sharply
to 18.3m in 2022 — a notable recovery worth further investigation.

**4. Monsoon recharge is uneven across states**
Maharashtra and Madhya Pradesh show strong post-monsoon recovery (recharge works
well there), while Gujarat and Haryana show little difference between pre- and
post-monsoon depth — meaning monsoon rainfall isn't sufficiently recharging
groundwater in these states.

**5. Madhya Pradesh and Maharashtra are the healthiest states**
Both states consistently show the lowest depth values (8–16m range) across all
7 states — indicating relatively accessible, healthier groundwater levels.

**6. Rajasthan is declining fastest per year; Karnataka is recovering fastest**
Trend analysis (linear fit) shows Rajasthan's water table dropping at +0.97 m/year —
the fastest decline of any state. Karnataka, in contrast, is improving at -0.73 m/year,
the fastest recovery.

## Methodology
- Loaded raw well-level data (5,490 wells) with `latin1` encoding
- Cleaned state names (removed LGD codes), converted invalid readings
  (e.g. 'Dry') to missing values
- Filtered out physically implausible readings (< 0m or > 100m)
- Reshaped data from wide to long format for analysis
- Computed state-year averages and fitted linear trends using `numpy.polyfit`
- Visualized findings using Matplotlib and Seaborn
