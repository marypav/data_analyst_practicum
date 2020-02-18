# Research: Determination of the prospective tariff for the Megaline telecom company

Project as part of Data Analyst course [Practicum by Yandex](https://practicum.yandex.com/data-analyst)

Megaline Company is a federal mobile operator. Customers are offered two tariff plans: Smart and Ultra. In order to adjust the advertising budget, the commercial department wants to understand which tariff brings more money.

It is necessary to make a preliminary analysis of tariffs on a small sample of customers. At your disposal are the data of 500 Megaline users: who they are, where they come from, what tariff they use, how many calls and messages each one sent in 2018. It is necessary to analyze customer behavior and conclude which tariff is better.

### Research questions
### Description of the sequence of actions
Description of the sequence of actions 
- Step 1. Learning General Information<br>
- Step 2. Data preprocessing
    - 2.1. Data Type Changes
    - 2.2. Search and Correction of Data Errors
    - 2.3. Counting for each user:
    - 2.3.1. The number of calls made and minutes spent talking per month;
    - 2.3.2. The number of messages sent by month;
    - 2.3.3. Monthly Internet traffic spent;
    - 2.3.4. Monthly revenue from each user<br>
- Step 3. Data Analysis
    - 3.1. Description of operator customer behavior based on the sample
    - 3.2. Calculation of average quantity, variance and standard deviation
    - 3.3. Distribution histograms
    - 3.4. Description of the resulting distributions<br>
- Step 4. Hypothesis Testing
    - 4.1. Hypothesis 1. The average revenue of users of the tariffs "Ultra" and "Smart" is different
    - 4.2. Hypothesis 2. The average revenue of users from Moscow differs from the revenue of users from other regions<br>
- Step 5. General conclusion

### Research Results
**General results**<br>
Based on the analysis of customer behavior of the federal mobile operator Megaline, the following conclusions can be drawn:
- For users, the Smart tariff is more profitable, since:
    - Users connected to the Smart tariff spend about 429 minutes per month on phone calls. Since the tariff limit is 500 minutes of conversation, users fit into the framework of the tariff plan;
    - Users connected to the Smart tariff spend about 33 messages per month. Since the tariff limit is 50 messages, users still have most of the unused messages within the tariff.
    - Users connected to the Smart tariff spend about 16237 mb = 15gb per month. Since the tariff limit is 15 GB, users fit into the framework of the tariff plan.

- For the mobile operator, the Ultra tariff is more profitable, since:
    - Users connected to the Ultra tariff plan spend about 540 minutes per month on telephone calls. Since the tariff limit is 3000 minutes of conversation, users still have most of the minutes within the tariff;
    - Users connected to the Ultra tariff plan spend about 49 messages per month. Since the tariff limit is 1000 messages, users still have most of the unused messages within the tariff;
    - Users connected to the Ultra tariff spend about 19488 mb = 19gb per month. Since the tariff limit is 30 GB, users still have most of the unused Internet traffic within the tariff.
    - In general, all users of the Ultra tariff always have a portion of unspent minutes, sms and Internet traffic.
    
Of the two hypotheses, only the first was confirmed:
**Average revenue of Ultra and Smart tariff users differs**

**Recommendations to the mobile operator:**
- It is necessary to correct rounding / track the correctness of the unloading of signs with zero values in the columns;
- Nudy knowledge in the sign **minutes** and **mb** should be rounded to 1;
- It is necessary to optimize the Ultra tariff, since most of the services under this tariff remain unencumbered.
<br>

**Description of the resulting distributions:** <br>
**1. Analysis of call data and minutes of conversation** <br>
Normal distribution is determined by the mean and variance. They let you know how noisy the data is now. <br>

* Users connected to the Smart tariff spend about **429 minutes** per month on phone calls. Since the tariff limit is 500 minutes of conversation, users fit into the framework of the tariff plan.
* Users connected to the Ultra tariff plan spend about **540 minutes** per month on phone calls. Since the tariff limit is 3000 minutes of conversation, users still have most of the minutes within the tariff.

**2. Message Data Analysis** <br>
Normal distribution is determined by the mean and variance. They let you know how noisy the data is now. <br>

* Users connected to the Smart tariff spend about **33 messages** per month. Since the tariff limit is 50 messages, users still have most of the unused messages within the tariff.
* Users connected to the Ultra tariff plan spend about **49 messages** per month. Since the tariff limit is 1000 messages, users still have most of the unused messages within the tariff.

**3. Web traffic analysis** <br>
Normal distribution is determined by the mean and variance. They let you know how noisy the data is now. <br>

* Users connected to the Smart tariff spend about **16237 mb** = 15gb per month. Since the tariff limit is 15 GB, users fit into the framework of the tariff plan.
* Users connected to the Ultra tariff plan spend about **19488 mb** = 19gb per month. Since the tariff limit is 30 GB, users still have most of the unused Internet traffic within the tariff.


## Authors

**Maria Pavlenko** <br>
[Facebook](https://www.facebook.com/pavlenko.mary), [LinkedIn](https://www.linkedin.com/in/mspavlenko/), [GitHub](https://github.com/marypavlenko)




