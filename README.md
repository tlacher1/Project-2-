# Project-2 proposal 
This project is designed to enhance ETL ( Extract, Transform, Load) skills. The topic for the project proposal is drug overdose with special emphasis on opioid mortality across thirty three states in United States. Further data will explore the relationship of overdose death rate with race, the prescription rate of opioid, along with change in prescription rate in past one year and five years. The opioid related open databases will be accessed from Center for Disease Control and Prevention (CDC), Medicare and Medicaid services. 

[CDC Data](https://www.cdc.gov/drugoverdose/fatal/dashboard/index.html)

[Medicare data](https://data.cms.gov/summary-statistics-on-use-and-payments/medicare-medicaid-opioid-prescribing-rates/medicare-part-d-opioid-prescribing-rates-by-geography/data)

[Medicaid data](https://data.cms.gov/summary-statistics-on-use-and-payments/medicare-medicaid-opioid-prescribing-rates/medicaid-opioid-prescribing-rates-by-geography/data)  

The databases from these three sources will be extracted, transformed, and then uploaded as relational database using PostgreSQL and pgAdmin.

# Project-2 report

### Extract
The opioid related open databases was accessed from Center for Disease Control and Prevention (CDC), Medicare and Medicaid services. Through these three sources three databases were extracted

[CDC Data](https://www.cdc.gov/drugoverdose/fatal/dashboard/index.html)

[Medicare data](https://data.cms.gov/summary-statistics-on-use-and-payments/medicare-medicaid-opioid-prescribing-rates/medicare-part-d-opioid-prescribing-rates-by-geography/data)

[Medicaid data](https://data.cms.gov/summary-statistics-on-use-and-payments/medicare-medicaid-opioid-prescribing-rates/medicaid-opioid-prescribing-rates-by-geography/data)  

### Transform
* Jupyter notebook was used to run panda to create dataframe and for creating rich text elements explaning each step of coding.
* The Sudors CDC data was in excel format, so it was first converted to CSV format. The rest two data files were already in CSV format. The raw data was imported in the Jupyter notebook databases from these three sources. 
* The data was filterd for the year 2020 and the States names. 
* For all the three dataframes, the columns which are of interest were retained. The columns were further renamed to ensure the consistency in the nomenclature of all three databases. 
* The duplicates and missing data were removed. 
* The data was formatted to standardized format - percentages were removed from ,expanded decimal range, removed commas from number format, column header were reworded in lowercase to be compatible with pgadmin.
* AFter every formatting, the "count" command is run to ensure seamless transition of all the data
* The index was reset to the name of the States. 

### Load
Using pgadmin, the three dataframes were used to create three relational tables. The three tables were representing CDC drug overdose, Medicare, and Medicaid data.  
