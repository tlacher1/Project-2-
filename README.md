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
* In Jupyter notebook, we used panda to read in the csv files, create the dataframes and comment on each step of coding process.
* The Sudors CDC data was in excel format, so it was first converted to CSV format. The rest two data files were already in CSV format. The raw data was imported in the Jupyter notebook databases from these three sources. 
* The data was filtered for the year 2020 and States names. 
* For all the three dataframes, the columns which are of interest were retained. The columns were further renamed to ensure the consistency in the nomenclature of all three databases. 
* The duplicates and missing data were removed. 
* The data was formatted to standardized format - percentages were removed from ,expanded decimal range, removed commas from number format, column header were reworded in lowercase to be compatible with pgadmin.
* After every formatting, the "count" command is run to ensure seamless transition of all the data
* The index was reset to the name of the States. 

### Load
Using pgadmin, the three dataframes were used to create three relational tables. The three tables were representing CDC drug overdose, Medicare, and Medicaid data. Depending on research question, the data query can be run for aggregation of the three tables or an individual table. For example to examine the relationship between Opioid overdose death ( Sudors table) and Opioid presecription rates ( Medicare and Medicaid table), the data query can be run to aggregate the required data from three tables.  

***Coding for Creating tables in pgadmin***

CREATE TABLE MEDICARE_OPIOID_PRESCRIBING_RATE(

	id text,
	
	year int,
	
	Breakout text,
	
	Tot_Opioid_Clms bigint,
	
	LA_Tot_Opioid_Clms bigint,
	
	LA_Opioid_Prscrbng_Rate decimal(4,2),
	
	LA_Opioid_Prscrbng_Rate_5Y_Chg decimal(4,2),
	
	LA_Opioid_Prscrbng_Rate_1Y_Chg decimal(4,2)
	
);

CREATE TABLE MEDICAID_OPIOID_PRESCRIBING_RATE(

	id text,
	
	year int,
	
	Plan_Type text,
	
	Tot_Opioid_Clms bigint,
	
	LA_Tot_Opioid_Clms bigint,
	
	LA_Opioid_Prscrbng_Rate decimal(4,2),
	
	LA_Opioid_Prscrbng_Rate_5Y_Chg decimal(4,2),
	
	LA_Opioid_Prscrbng_Rate_1Y_Chg decimal(4,2)
	
);

CREATE TABLE SUDORS_Fatal_Overdose_Data(

	id TEXT,
	
	year INT,
	
	alldrug_deaths INT,
	
	opioids_deaths INT,
	
	opioids_rate decimal(10,5),
	
	rxopioids_deaths INT,
	
	rxopioids_rate decimal(10,5),
	
	opioids_percent decimal(10,5),
	
	male_deaths INT,
	
	male_percent decimal(10,5),
	
	female_deaths INT,
	
	female_percent decimal(10,5),
	
	black_nh_deaths INT,
	
	black_nh_percent decimal(10,5),
	
	white_nh_deaths INT,
	
	white_nh_percent decimal(10,5),
	
	hisp_deaths INT,
	
	hisp_percent decimal(10,5)
	
	);

***Loaded the dataset into the tables - see images of three relational tables below***

![image](https://user-images.githubusercontent.com/109105878/209028745-75bb8853-bd11-4ad3-9b35-ca22edbc7373.png)


![image](https://user-images.githubusercontent.com/109105878/209028814-3f22600c-b8e9-4249-a688-bf6ba9049248.png)

![image](https://user-images.githubusercontent.com/109105878/209028824-a5caab63-018e-47cb-acae-f9105387a53b.png)


