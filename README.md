# Covid-Vaccination-Analytics

about the files

| Filename | Desc | 
| --------- | --------- | 
| Data_cleaning saving to SQL and CSV.ipynd | This file is resp. for cleaning the data and saving it to SQL and CSV formats |
| covid_data_cleaned.csv | Thsi is the CSV output file from the notebook |
| Covid_Vaccination Progress Dashboard.twb | The Tableau live workbook |
| Images | the background Image of tableau is gathered from this file |

Thanks to [brian-mcgowan](https://unsplash.com/photos/pink-and-black-hearts-illustration-7OabDHeImsA) for the backgorund image from unsplash

 

# 1. The data contains the following information:

###     1. Country- this is the country for which the vaccination information is provided;

###     2. Country ISO Code - ISO code for the country;

###    3. Date - date for the data entry; for some of the dates we have only the daily vaccinations, for others, only the (cumulative) total;

###     4. Total number of vaccinations - this is the absolute number of total immunizations in the country;

###     5. Total number of people vaccinated - a person, depending on the immunization scheme, will receive one or more (typically 2) vaccines; at a certain moment, the number of vaccination might be larger than the number of people;

###     6. Total number of people fully vaccinated - this is the number of people that received the entire set of immunization according to the immunization scheme (typically 2); at a certain moment in time, there might be a certain number of people that received one vaccine and another number (smaller) of people that received all vaccines in the scheme;

###     7. Daily vaccinations (raw) - for a certain data entry, the number of vaccination for that date/country;

###     8. Daily vaccinations - for a certain data entry, the number of vaccination for that date/country;

###     9. Total vaccinations per hundred - ratio (in percent) between vaccination number and total population up to the date in the country;

###     10. Total number of people vaccinated per hundred - ratio (in percent) between population immunized and total population up to the date in the country;

###     11. Total number of people fully vaccinated per hundred - ratio (in percent) between population fully immunized and total population up to the date in the country;

###     12. Number of vaccinations per day - number of daily vaccination for that day and country;

###     13. Daily vaccinations per million - ratio (in ppm) between vaccination number and total population for the current date in the country;

###     14. Vaccines used in the country - total number of vaccines used in the country (up to date);

###     15. Source name - source of the information (national authority, international organization, local organization etc.);

####     Source website - website of the source of information;


    
# Dashboard Requirements
    1. Dashboard should show the dailyy trends with filter based on countries
    2. How many people in every hundred people are fully vaccinated, partially vaccinated, booster dosed
    3. Which countries is the lowest fully vaccinated, partially vaccinated, booster dosed
    4. which countries have the lowest vaccinated people per million 
    5. What is the Percentage of people fully vaccinated, Partially Vaccinated and booster dosed
    6. Month over month vaccination change percentage .
    7. 
    
# Notes for tableau workbook

## Tableau calculated feilds:

### 1. c_1_dosed = sum({INCLUDE  [Location]: MAX([People Vaccinated])})   ✔️
    This gives the output as 562,93,69,680 or 5.62B  
    for p_country = 'All'    --> 5.62B
    for p_country = 'China'  --> 1.31B
### 2. c_2_dosed = sum({INCLUDE  [Location]: MAX([People Fully Vaccinated])})
    for p_country = 'All'    --> 5.18B
    for p_country = 'China'  --> 1.28B
### 3. c_booster_dosed = sum({INCLUDE  [Location]: MAX([Total Boosters])})
    for p_country = 'All'    --> 2.80B
    for p_country = 'China'  --> 0.83B

### 4. while I was making indicator for "Vaccinations per hundred" I encountered a problem there are columns such as [total_vaccinations_per_hundred,	people_vaccinated_per_hundred, people_fully_vaccinated_per_hundred	, total_boosters_per_hundred] which has values greater than 100 for 100 population which i think is not possible.

    So, I replaced the values for these columns which are greater that 100 to 100

    
