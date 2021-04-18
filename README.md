# Final project - data mining - April 18th, 2020
Benjamin Kolber 
Jonathan Bofman


## Summary:
For our project we decided to take a look at education, degree's, economic success and marriage. We targeted this report to incoming students and tried to demystify the importance of degree w.r.t income, and wether money and education can affect a person's chance of getting married or getting a divorce. 

## Files:

final_code.ipynb - all code for exploration, discovery and modeling. 
final_report - our submitted final report
critique - our critique on Efe Alonge and Ido Li On's project. 

## Data Extraction:

1. go to IPUMS.org/usa
2. Select the features as described by the 'additional resources' section in the final_report (last 3 pages)
3. request a data extract
4. download the .XML and .dat file onto your desktop and run the following code:

install.packages('ipumsr')")
ipums_conditions()

setwd("~/Desktop")
ddi <- read_ipums_ddi(<downloaded XML file>)
data <- read_ipums_micro(ddi)

drops <- c("SAMPLE", "SERIAL", "CBSERIAL", "HHWT", "CLUSTER", "STRATA", "GQ", "DEGFIELDD")
data = data[ , !(names(data) %in% drops)]

write.csv(data,"IPUMS.csv", row.names = FALSE)
