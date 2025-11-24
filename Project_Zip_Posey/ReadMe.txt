Project Title: Understanding Flight Delays in America: A Data-Driven Review of 2019–2020

Student: Sofia Posey
Course: Foundations of Data Analytics
Instructor: Alexandra Desaulniers
Date: 11/20/2025

1. Project Overview
This project analyzes U.S. domestic flight delays for 2019–2020 using data originally published by the U.S. Department of Transportation (Bureau of Transportation Statistics) and obtained through a Kaggle dataset.
The report examines:

- How delays vary across airlines and states
- The relationship between traffic volume (number of flights) and delays
- The distribution of delay causes (carrier, NAS, weather, security, late aircraft)
- Differences between 2019 and 2020, including the impact of reduced traffic in 2020

All analyses and figures were produced in R using a cleaned version of the original dataset.

2. Folder Structure
Project_Zip_Posey/
├── Data/
│   ├── ReadMe_Data.txt        
│   └── airline_delay.csv    
│
├── Proposal/
│   └── Proposal_Idea_Posey.docx        
│
├── Project/
│   ├── Report_Posey.Rmd       
│   └── Report_Posey.nb.html   
│
├── Presentation/
│   └── Presentation_Posey.pdf    
│
└── ReadMe.txt                 # This file

3. How to Run the Analysis

	1. Open Project/Report_Posey.Rmd in RStudio.

	2. Ensure the Data files are in the Data/ subfolder relative to the Rmd (as in the structure above).

	3. Install/load any required packages listed at the top of the Rmd (e.g., tidyverse, dplyr, ggplot2, lubridate, etc.).

	4. Knit the document to HTML. This will reproduce the cleaned data frame, all summary tables, and all figures shown in Report_Posey.nb.html.

4. Data Source

A more detailed description of the dataset, including variable definitions and the exact URL to the original Kaggle source, is provided in Data/ReadMe_Data.txt.
In summary, the data consist of aggregated monthly arrival statistics by airline and airport, including:
- Counts of on-time, delayed, cancelled, and diverted flights
- Delay minutes broken down into carrier, weather, NAS, security, and late-aircraft causes
- Percentages of delayed flights attributable to each cause

5. Contact / Notes

If any paths break when knitting the R Markdown file, check that the working directory is the Project_Zip_Posey/ folder and that the Data/ subfolder is intact.

All figures used in the presentation are generated directly from the R Markdown report.