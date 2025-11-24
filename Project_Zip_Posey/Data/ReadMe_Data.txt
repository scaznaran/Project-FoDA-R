Understanding Flight Delays in America: A Data-Driven Review of 2019–2020
Data ReadMe
Last updated: 11/20/2025

--------------------------------------------------
1. FILES INCLUDED
--------------------------------------------------

- airline_delay.csv  
  Original CSV file downloaded from Kaggle and used as the raw input for the project.

--------------------------------------------------
2. DATA SOURCE
--------------------------------------------------

Original data provider:  
- U.S. Department of Transportation, Bureau of Transportation Statistics (BTS).

Accessed via Kaggle dataset:  
- Title: Airline Delays  
- URL: https://www.kaggle.com/datasets/eugeniyosetrov/airline-delays

The Kaggle file is based on BTS On-Time Performance statistics and aggregates arrival outcomes by carrier, airport, and time period.

--------------------------------------------------
3. DATA DESCRIPTION
--------------------------------------------------

Unit of observation (row):  
- Each row represents a combination of YEAR, MONTH, AIRLINE CARRIER, and AIRPORT, with aggregated counts and delay measures for that combination.

Time coverage:  
- 2019–2020 (U.S. domestic flights only).

Geographic coverage:  
- U.S. airports (50 states and Washington, D.C.).  
- After cleaning, only rows with valid U.S. state abbreviations are retained.

Key variables (short list):
- year: Calendar year of the observation (integer).
- month: Calendar month of the observation (integer, 1–12).
- carrier: Two-letter carrier code (character).
- carrier_name: Full name of the airline (character).
- airport: Airport code (IATA code, three letters).
- airport_name: Full airport name (original; later split into city, state, and airport_name).
- arr_flights: Number of on-time arriving flights for that carrier–airport combination (integer, interpreted based on BTS documentation).
- arr_del15: Number of flights that arrived 15 or more minutes late (integer).

Percent of delayed flights by cause (floats, 0–100 or 0–1 depending on original coding):
- carrier_ct: Percent of delayed flights (`arr_del15`) attributed to carrier-related causes.
- weather_ct: Percent of delayed flights attributed to weather.
- nas_ct: Percent of delayed flights attributed to National Aviation System (NAS) issues.
- security_ct: Percent of delayed flights attributed to security problems.
- late_aircraft_ct: Percent of delayed flights attributed to late-arriving aircraft.

Delay minutes by cause (integers, minutes):
- arr_delay: Total delay minutes for all delayed flights.
- carrier_delay: Delay minutes due to carrier-related causes.
- weather_delay: Delay minutes due to weather.
- nas_delay: Delay minutes due to NAS causes.
- security_delay: Delay minutes due to security issues.
- late_aircraft_delay: Delay minutes due to late-arriving aircraft.

Other counts:
- arr_cancelled: Number of cancelled flights.
- arr_diverted: Number of diverted flights.

(Full variable list and detailed descriptions are provided in the variable dictionary within the R Markdown report.)

--------------------------------------------------
4. MISSING DATA AND CLEANING NOTES
--------------------------------------------------

- The original CSV contains some rows with missing (NA) values in key numerical fields.
- For the analysis, rows with any NA values were removed using complete-case filtering.
- The original `airport_name` field in the CSV combines city, state abbreviation, and airport name in a single string.  
  In the analysis, this field is split into three variables:
    - city
    - abbr (state abbreviation)
    - airport_name (cleaned airport name)
- Only records with valid U.S. state abbreviations (50 states plus DC) are retained.

These cleaning steps are implemented in the R Markdown report (`FinalProject_Posey.Rmd`) and are not directly applied to the original CSV file, which is preserved here for reference.

--------------------------------------------------
5. HOW TO USE THIS DATA
--------------------------------------------------

Example R code to load the original CSV:

    airlines <- read.csv("Data/airline_delay.csv", stringsAsFactors = FALSE)

The analysis uses this file as input, performs the cleaning described above, and then generates summary tables and visualizations for flight delays by airline, state, and cause.

--------------------------------------------------
6. LIMITATIONS
--------------------------------------------------

- The dataset is a subset of the full BTS on-time performance database and may not include all U.S. flights.
- Delay causes are based on airline reporting and may be subject to reporting error or categorization differences.
- Percent variables and total counts are aggregated at the month–carrier–airport level, so individual flight-level details are not available.
