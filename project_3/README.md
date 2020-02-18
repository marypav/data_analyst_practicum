# Research: Sale of apartments in service Yandex.Realty

Project as part of Data Analyst course [Practicum by Yandex](https://practicum.yandex.com/data-analyst)

Yandex.Realty aggregates listings from the largest and most reliable real estate websites and realtor databases. It maintains the quality of information it provides and, in result, the users see only those offers that can be trusted. Yandex.Realty filters out outdated and merges duplicate ads, checks the price and location of the property on offer.

At our disposal are Yandex.Real Estate service data - an archive of advertisements for the sale of apartments in St. Petersburg and neighboring settlements for several years. We research how to determine the market value of real estate. Our task is to set the parameters. This will allow our to build an automated system: it will track anomalies and fraudulent activities.

For each apartment for sale, two types of data are available. The former are entered by the user, the latter are obtained automatically based on cartographic data. For example, the distance to the center, the airport, the nearest park and a pond.

**Data Description**
- **airports_nearest** — distance to the nearest airport in meters (m);
- **balcony** — number of balconies;
- **ceiling_height** — ceiling height (m);
- **cityCenters_nearest** — distance to the city center (m);
- **days_exposition** — how many days the ad was posted (from publication to withdrawal);
- **first_day_exposition** — publication date;
- **floor**;
- **floors_total** — total floors in the house;
- **is_apartment** — apartments (boolean type);
- **kitchen_area** — kitchen area in square meters (m²);
- **last_price** — price at the time of withdrawal from publication;
- **living_area** — living area in square meters (m²);
- **locality_name** — name of the settlement;
- **open_plan** — free layout (boolean type);
- **parks_around3000** — the number of parks within a radius of 3 km;
- **parks_nearest** — distance to the nearest park (m);
- **ponds_around3000** — the number of reservoirs within a radius of 3 km;
- **ponds_nearest** — distance to the nearest body of water (m);
- **rooms** — number of rooms;
- **studio** — studio apartment (boolean type);
- **total_area** — apartment area in square meters (m²);
- **total_images** — the number of photos of the apartment in the ad.

### Research questions
### Description of the sequence of actions
- Step 1. Learning General Information<br>
<br>
- Step 2. Data preprocessing<br>
    - 2.1. Defining and filling in missing values<br>
    - 2.2. Data Type Changes<br>
<br>    
- Step 3. Counting and adding data to the table<br>
    - 3.1. Count and add to the table: price per square meter;<br>
    - 3.2. Calculate and add to the table: day of the week, month and year of publication of the announcement;<br>
    - 3.3. Count and add to the table: apartment floor; options - first, last, other;<br>
    - 3.4. Calculate and add to the table: the ratio of living and total area, as well as the ratio of the area of the kitchen to the total;<br>
    - 3.5. To study the parameters: area, price, number of rooms, ceiling height;<br>
    - 3.6. Build histograms for each parameter: area, price, number of rooms, ceiling height.<br>
<br>    
- Step 4. Conducting research data analysis<br>
    - 4.1. Task 1. Study the time of sale of apartments.<br>
    - 4.2. Task 2. Remove rare and outdated values.<br>
    - 4.3. Task 3. What factors most affect the value of the apartment?<br>
    - 4.4. Task 4. Study the offers of apartments in St. Petersburg<br>
    - 4.5. Task 5. Select the segment of apartments in the center.<br>
<br>
- Step 5. General conclusion<br>


### Research Results

**General results**<br>

- There are no duplicates in the data set;
- There are many missing data in the dataset. In such columns as: ceiling_height (9195), floors_total (86), living_area (1903), is_apartment (20924), kitchen_area (2278), balcony (11519), locality_name (49), airports_nearest (5542), cityCenters_nearest (5519), parks_around3000 (5518), parks_nearest (15620), ponds_around3000 (5518), ponds_nearest (14589), days_exposition (3181);

- In the column describing the height of the ceilings in apartments for sale (ceiling_heigh) - 9195 missing values filled the gaps with the median value for the column. On average, the ceiling height in apartments from the table data proposed for analysis = 2.77 (m). Interestingly, the maximum value in the column is the height of the ceilings: 100.00 (m), this is the height of the ceilings.

- In the column describing the number of floors in the house (floors_total) - 86 missing values, filled the gaps with a value of 1. Even if our assumption is wrong, 86 records should not greatly shift the distribution.

- In the column describing the living area in square meters (m²) (living_area) - 1903 missing values filled in the missing values with a median value.

- In the column describing the apartment as an apartment (is_apartment) - 20924 missing values. The values of the missing were replaced by False - the apartment is not an apartment. I did not change the data type in the column because I believe that the values True and False more clearly represent the relation of the property to the type of apartment.

- In the column describing the area of the kitchen in square meters (m²) (kitchen_area) - 2278 missing values, filled in the missing values with a median value.

- In the column describing the presence of a balcony (balcony) - 11519 missing values, filled with 0.0 values. She suggested that these are single-story houses, since she did not know either the building plan or the builder.

- In the column the name of the locality (locality_name) - 49 missing values, filled the values with the fact that the information for these values is not undefined (undefined). Since the name of the area does not correlate with other signs.

- In the columns, the distance to airports (airports_nearest) - 5 542 missing values and in the column the distance to the city center (cityCenters_nearest) 5 519 missing values. We fill in the data with the median value, for 336 lines it was not possible to fill in the values. In these cases, most likely, gaps appear in settlements that are not cities or are sufficiently far from cities. Or there is no data for calculating distances.

- In the columns, the number of parks within a radius of 3 km (parks_around3000), the distance to the nearest park (m) (parks_nearest), the number of reservoirs within a radius of 3 km (ponds_around3000), the distance to the nearest reservoir (m) (ponds_nearest): the number of missing values is 5518, 15620, 5518, 14589. Checked the correlation with other parameters, it turned out to be insignificant from 0.0005 to 0.3. Since the correlation with other parameters for all 4 parameters is low. It can be said that the values of these columns are independent of other quantities. She added information that for missing values in these columns, the value is not defined, as this will not affect the analysis.

- In the column describing the number of days of placing an advertisement for the sale of an apartment was posted (days_exposition) - 3181 missing values. For each missing value, it calculated the median value and the median value filled in the gaps. Before filling in the blanks in the days_exposition column, convert the first_day_exposition column to the data type% Y-% m-% d, because the days_exposition column depends on the date the ads were posted.

**Calculation results:**
- The price per square meter for all apartments provided in the data table was 108,395 rubles.
- Most often there are proposals for the sale of apartments not on the first and last floors. The number of such apartments in the total sample according to the data amounted to 17,446 apartments
- The ratio of residential represented apartments to the total area of apartments: 56.50%
- The ratio of the area of the kitchen of the presented apartments to the total apartments: 17.28%
- The most popular apartments are apartments with a total area of 40 sq. M to 60 sq. M.
- Also, the most popular apartments are one-room and two-room apartments.
- Most often, the ceiling height of the apartments in demand on the market is 2.6 m
- The cost of the most popular apartments on the market is 5,000,000 rubles.

**General conclusion:**
So I examined the sample provided by the Yandex.Real Estate service:
- Studied the data on sales of apartments;
- categorized and restored data;
- Found patterns in the data and filled all the gaps;
- Built graphs of the dependence of the price of the apartment on its parameters;
- In the sample, the city with the largest number of advertisements for the sale of apartments was found;
- Highlighted a segment of ads that are sold in the center of St. Petersburg;
- The dependence of the price of the apartment on its parameters for the city center has been determined.

The parameters that directly affect the cost of the apartment are defined:
- Location of the apartment (city / suburb, center / non-center);
- Number of rooms
- Living area of the apartment;
- number of rooms;
- Minor data such as “ceiling height, publication date” have little impact on pricing.


## Authors

**Maria Pavlenko** <br>
[Facebook](https://www.facebook.com/pavlenko.mary), [LinkedIn](https://www.linkedin.com/in/mspavlenko/), [GitHub](https://github.com/marypavlenko)



