# Data Generation
## Random Data Generation With Command Line Option



### Some design thoughts on data generation:

  To make data resemble real-life tax data we assume the scenario where some percentage of people paying tax in next year are new (5%) and some people may miss out or not pay the taxes in a year. The data generation script mimics this assumption by carrying over 80% of the taxpayers information and generates a random tax amount. The generator script creates 20% data for a year that are new compared to the previous year’s generation.
  
  In many cases, data generated may have missing or incomplete information. The data generator script mimics this scenario by randomly choosing null fields for 20% of the data generated for a year. 



### Steps we follow to generate the data:

  The record generator will generate random records for all six fields(ID, Name, Tax amount, Year, Zip Code, Household). However, we use USA zip code file to take random zip code for each person which is “zipcodes.txt”

  We generated a random null value for a random field and did calculations that look data realistic. In this calculation, we generate a 20% null value which is used for the further part “cleaning”.

  We generate base data first which includes one-year data for a random person. The output of this base only data will be used as a seed input for further 20GB data generation. 

  The output of the base only data “seed file” is used as a seed input for the next 20 GB data generation.
  
  In the seed 2GB input, we have all fields. We use 80% of that field such as a person’s ID, Name, and zip code in the future data, and put random data for the Tax amount and household. However, generate 20% of new data with all six fields.



### The command-line options to generate the data:

  -z  :- zip code file which contains all US zip codes. Here it is “zipcodes.txt”
  
  -o  :- output directory where data will be generated in CSV format.
  
  -n  :- number of records per year 
  
  --seed-dir  :- output of the base only data
  
  --base-year  :- it starts generating data from whatever founds here. (i.e 2004)
  
  --num-years  :- Total number of years from which to generate records. The year will start from 2000.
  
  --base-only  :- pass this when we want to generate only base data  
  


