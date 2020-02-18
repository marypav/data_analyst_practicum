# Research: Assessing the reliability of borrowers of bank

Project as part of Data Analyst course [Practicum by Yandex](https://practicum.yandex.com/data-analyst)

**Customer**
credit department of the bank. You need to find out whether the marital status and the number of children of the client affects the fact of repayment of the loan on time. Input data from the bank - statistics on the solvency of customers.
The results of the study will be taken into account when building the model of credit scoring - a special system that evaluates the ability of a potential borrower to repay a loan to a bank.

**Data Description:**
* **children** - the number of children in the family
* **days_employed** - total work experience in days
* **dob_years** - customer age in years
* **education** - customer education level
* **education_id** - educational level identifier
* **family_status** - marital status
* **family_status_id** - identifier of marital status
* **gender** - customer gender
* **income_type** - type of employment
* **debt** - whether there was a loan repayment debt
* **total_income** - monthly income
* **purpose** - the purpose of obtaining a loan.

### Research questions
* Is there a relationship between having children and repaying a loan on time?
* Is there a relationship between marital status and repayment of the loan on time?
* Is there a relationship between income and repayment of the loan on time?
* How do different loan objectives affect repayment on time?

### Research plan
1. Connection of the pandas library
2. Read the data from the data.csv file
3. View the size of the data table
4. View general data information in data
5. Viewing the first 10 rows of the data table
6. View the last 10 rows of the data table
7. View a list of column names
8. Search and view the number of duplicates in the data dataset
9. Search and view the number of empty values in the data set <br>
**We study the data for each of the columns:**
10. Data column children. Let's calculate the number of children in the families of borrowers of the bank
11. Data column days_employed. We will calculate the total number of days of experience of borrowers
12. Data column days_employed. Let's look at the data display in the column
13. The data in the dob_years column. We will calculate the total number of days of borrower experience in years
14. Data column education. Let's count the number of borrowers with different levels of education
15. Data column family_status. Let's count the number of borrowers with different marital status
16. Data column gender. Let's count the number of borrowers of different sexes
17. Data column income_type. Let's count the number of borrowers of different types of employment
18. Data column total_income. Let's see if there are borrowers without income
19. Data column total_income. We will calculate the monthly income of all borrowers
20. Data column total_income. Let's see the missing values
21. Data column purpose. Let's see the number of different goals of borrowers <br>
**Conclusion on the studied data**


### Research Results

**Hypotheses:**<br>
* Music in two cities - Moscow and St. Petersburg - listen in different modes;
* Lists of the ten most popular genres on Monday morning and Friday evening have characteristic differences;
* The population of the two cities prefers different musical genres.

**General results**<br>

* In the data set data 21 525 records, 12 columns;
* Duplicates in the data set - 54;
* Children column:
    * 47 records (information on the number of children of borrowers) in the column children = -1.
    * These data must be deleted, as they will not give us the correct results;
    * 76 entries (information on the number of children of borrowers) in the column children = 20.
    * This is most likely a mistake, this data will also be deleted from the analysis;
* Days_employed column:
    * 2 174 passes in the days_employed and total_income columns;
    * In the days_employed column, the data type is float64, the number of negative values ​​in the column = 15906.
    * It is necessary to change the data type in the column to int64 and make absolute values;
* Dob_years column:
    * 101 records (borrower age) in the dob_years = 0 column.
* Education column:
    * In the column education there are categories written in a different register, it is necessary to bring to a single look.
* Column family_status:
    * In the column family_status one category it is necessary to bring the writing of all categories to a single form.
* Purpose column:
    * In the purpose column, there are various formulations of the same goals, it is necessary to lead to a uniform view by applying lemmatization.

**Assumption of gaps and negative data values:**
* There are 76 entries in the children column (information on the number of children of borrowers) in the children = 20. column. This is extremely suspicious, I would like to clarify with the person who provided me the data, which means the value 20. My guess about this value was that the children 2 and 0 it was added by mistake, but again I can’t clarify this - therefore deleted 76 records;
* In the days_employed and total_income columns, the same amount of missing data = 2 174. In my opinion, these columns are interconnected, because on the basis of days_employed we calculate total_income. The reasons for missing data in these columns may depend on the employer who provides data on the number of days worked. And here the employer may not be honest and enter one in the work book and in the statements, and tell the employee another.

**The resulting debt probabilities:**
* income in the range from 107.6 to 142.6 thousand rubles per month = 9.0%
* income in the range from 142.6 to 195.8 thousand rubles = 8.5%
* income less than or equal to 107.6 thousand rubles. = 8.0%
* more than 195.8 thousand rubles = 7.0%

* Borrowers with the highest income (more than 195.8 thousand rubles) are less likely to be in debtors, the percentage of loan debtors is ≈ 7.0%.
* Borrowers with a low level of income (income less than or equal to 107.6 thousand rubles), as well as borrowers with the highest income, try to pay off loans on time, so for borrowers from the group with the lowest income, the percentage of debtors on loans is ≈ 8 , 0%. This can be explained by the fact that people with the lowest incomes are better at managing their funds and are able to control their budget than those who earn a little more.
* Borrowers with an average income level from 107.6 to 142.6 thousand rubles a month remain in debt on loans with a percentage of ≈ 9.0%.
* Borrowers with an income level of 142.6 to 195.8 thousand rubles have, the percentage of debtors on loans ≈ 8.5%

Thus, loan repayment depends on the income level of borrowers. The higher the income of borrowers, the less% of loan arrears.




## Authors

**Maria Pavlenko** <br>
[Facebook](https://www.facebook.com/pavlenko.mary), [LinkedIn](https://www.linkedin.com/in/mspavlenko/), [GitHub](https://github.com/marypavlenko)


