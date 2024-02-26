# Credit-EDA-Assignment

# Business Understanding :
The loan providing companies find it hard to give loans to the people due to their insufficient or non-existent credit history. Because of that, some consumers use it to their advantage by becoming a defaulter. Suppose you work for a consumer finance company which specialises in lending various types of loans to urban customers. You have to use EDA to analyse the patterns present in the data. This will ensure that the applicants capable of repaying the loan are not rejected.
When the company receives a loan application, the company has to decide for loan approval based on the applicant’s profile. Two types of risks are associated with the bank’s decision:
- If the applicant is likely to repay the loan, then not approving the loan results in a loss of business to the company
- If the applicant is not likely to repay the loan, i.e. he/she is likely to default, then approving the loan may lead to a financial loss for the company.

The data given below contains the information about the loan application at the time of applying for the loan. It contains two types of scenarios:
- The client with payment difficulties: 
  he/she had late payment more than X days on at least one of the first Y instalments of the loan in our sample,

- All other cases: 
  All other cases when the payment is paid on time.

When a client applies for a loan, there are four types of decisions that could be taken by the client/company):
- Approved: 
The Company has approved loan Application
- Cancelled: 
The client cancelled the application sometime during approval. Either the client changed her/his mind about the loan or in some cases due to a higher risk of the client, he received worse pricing which he did not want.
- Refused: 
The company had rejected the loan (because the client does not meet their requirements etc.).
- Unused offer:  
Loan has been cancelled by the client but at different stages of the process.

In this case study, used EDA to understand how consumer attributes and loan attributes influence the tendency to default.

# Flow of the case study:

- 1) Reading and understanding datasets
- 2) Data Exploration and Cleaning (Application data)
- 3) Data Visualisation (Application data)
- 4) Data Exploration and Cleaning (Previous Application data)
- 5) Analysis and Visualisation - Merged Data (Application data + Previous Application data)
- 6) Recommendations and Conclusions
 
# Steps:

1) Understanding the data –
imported the data and understood the variables with the help of column description 
data.

2) Basic Sanity checks –
using info, shape, description commands to check the if the data is practically correct or 
not. Eg. If any column related to time/day is negative then it is to be corrected to positive, 
values exceeding the maximum permissible limit should be handled.

3) Identifying and Imputing/Removing missing values OR removing entire column –
checked the missing values with the help of “isna”, ”isnull” & sum or mean commands.
• If more than 40% data is missing from a variable then dropped that variable
• If less than 5% data is missing then the rows can be dropped but decided to ignore that values as data 
was quite large
• For missing data between 5% to 40%, if variable is categorical then checked if data is missing at random(in any specific pattern)
then imputed the data with appropriate value or with mode and for numerical variable imputed with appropriate measure of central tendency.
Note that we can even ignore the missing data in this category instead of imputing with the incorrect one.

4) Dropping unnecessary/irrelevant variables -
After observing the dataset and understanding the variables, we can drop the variables
which does not have much relevance with the objective of case study. For this we can use our 
domain knowledge along with data visualization.

5) Identifying & Handling Outliers –
Extreme values in a variable are called as outliers and it can be roughly observed with the 
help of describe command and further confirmed by plotting distribution plot or box plot.
Some outliers are due to data error (e.g. employment years = 1000) and some are practical 
values. Depending on the variable and outliers we can either impute or remove the outliers, 
  - bin them,
  - cap the data to certain percentile. e.g 1st to 99th or 5th to 95th.
  - use IQR to restrict the outliers.
Removed the outliers which were due to data error 

6) Standardizing Values –
Using info command we can observe the datatypes. Ensure that numerical columns have 
int or float datatype and categorical columns have categorical datatype. Changed the 
datatype where ever required.

7) Checking Data Imbalance –
Data imbalance is checking the percentage positive & negative outcome of the target 
variable in this case defaulters-1 & repayers-0.

8) Univariate, Categorical/Numerical Univariate Analysis –
Understanding each variable separately and wrt some category.
In this case, we found out the count of customers in a specific category wrt TARGET 
variable. We used pie chart, count plot, bar plot, distribution plot etc.

9) Bivariate & Multivariate Analysis –
Analyzing two or more variable at a time wrt target variable. The variables can be categorical 
or numerical or mix of both.
We used pairplot, boxplot, heatmaps, factorplot, bar plots etc.

# Some of the Important insights from EDA:
1) CODE_GENDER
   ![image](https://github.com/devendra2595/Credit_EDA_Assignment/assets/116253033/9f15a53a-8363-4b7f-8185-e71f206ec468)

- The number of female customers is almost double than number of male customers still the chances of male defaulting on a loan 
is higher than that of female.

2) INCOME_TYPE
   
   ![image](https://github.com/devendra2595/Credit_EDA_Assignment/assets/116253033/3ce907f7-141c-4c2d-9170-6ecb709451ff)

- It is least risky for the bank to give loan to businessman and students(0 default rate).
- Commercial associates, pensioner, state servant & working category fall under average rate of defaulting.
- the customers who are on Maternity leave have the highest possibility of defaulting. This is obvious because the expenses 
greatly increases in maternity period. Although, they have very low count as compared to other categories
- The people who are unemployed have the second highest default rate


3) EDUCATION_TYPE
   
   ![image](https://github.com/devendra2595/Credit_EDA_Assignment/assets/116253033/9e8b4f42-5847-47c4-9947-d3033e09c56b)


• Customers with academic degree have lowest rate of defaulting but the count is quite less as comparted to other categories.
• Lower secondary category has highest default rate (around 11%).
• secondary/secondary special have second highest default rate. they also contribute to the highest count.
• To reduce the default rate, bank should focus on Incomplete higher, Lower secondary & secondary/secondary special category 
customers as they have defaulting rate above avg(approx 8 %)

4) OCCUPATION
   
   ![image](https://github.com/devendra2595/Credit_EDA_Assignment/assets/116253033/bfc00d3a-b716-42e3-a037-000a10dd0a6e)

Note: (ignoring the Unknown category)
- Low-skilled Laborers have the highest defaulting rate (approx 17%) where as accountants have lowest defaulting rate (approx 5%).
- Laborers contribute to highest count of customers with 10.6 % defaulting rate


5) AGE_CATEGORY
   
   ![image](https://github.com/devendra2595/Credit_EDA_Assignment/assets/116253033/c9aa4a20-1cad-4256-a602-a270eca898bf)

* As age increases the possibility of defaulting decreases.
* Almost 50% customers belong to middle age category(40-60 years) who have default rate approx 7 %.
* Although very young customers(20-25 years) does not contribute much to the total count still they have the highest possibility of defaulting (>12%)
* Senior citizens are have lowest defaulting rate approx 5%.
* If we consider 2 categories, middle and young (25-60 years), they contribute to almost 85% of customers and have default rate in range 7 to 10 %. mojority of customers fall under this category.
* Young and middle age category affects the overall default rate.

6) Default rate in Gender Vs. Housing_type

   ![image](https://github.com/devendra2595/Credit_EDA_Assignment/assets/116253033/ec35989c-a891-4759-8256-50c74d3fa3da)

* Only in Office apartment category, male customers are less likely to default than females.
* In rest of the categories female customers are morte likely to repay loan.

7) Default rate in credit range Vs. age category

   ![image](https://github.com/devendra2595/Credit_EDA_Assignment/assets/116253033/0a2137bc-12b1-44ac-a85d-814a389207d0)

* It is interesting to observe that Very young customers have higher default rate than other age group customers they have not defaulted in above 2M loan amount. Here, the records to support this statement are below 50, still it is surprising.
* Above 2M credit category have relatively lower default rate than other categories across all age categories.
* Senior citizens are most likely to repay loans than any other age category.

8) Default rate in accompanied by and age category
   
   ![image](https://github.com/devendra2595/Credit_EDA_Assignment/assets/116253033/775a595e-7de8-4ea7-a5c5-0913c2f9c9b5)

* Senior citizen(above 60 years) who come with group of people are least likely to default and exactly opposite is the case with Very Young customers.


9) default rate - Income range vs. education type vs gender

    ![image](https://github.com/devendra2595/Credit_EDA_Assignment/assets/116253033/49a0e866-8fed-4699-a11e-fdcc316c1e3e)

* The values in each cell denotes the default percentage.
* We can say that Males with Salary range between 900K-1M with Secondary/Secaondary special education have highest possibility of defaulting
* Also Females with salary range between 400-500K with Lower secondary education have highest possibility of defaulting

10) Default rate- Contract type vs housing type
    ![image](https://github.com/devendra2595/Credit_EDA_Assignment/assets/116253033/34f6dbea-aacd-4873-b728-f23064f6d2fe)

11) Default rate- Income vs age category vs gender
    
   ![image](https://github.com/devendra2595/Credit_EDA_Assignment/assets/116253033/29029b98-8359-41af-a474-3d3eae22221e)

12) Contract Status Vs. Target (Merged Data)
   ![image](https://github.com/devendra2595/Credit_EDA_Assignment/assets/116253033/521907c5-7a83-40e1-a348-decba943e845)

- From previously approved loan, it is evident that the customers are least likely to default i.e ~7.5%. Although this
  category have highest number of customers.
- The customers whose loan was previously refused have defaulted the most in currently approved loan(~12%) but on
  the brighter side, 88% are repayers. If we decide to reject on the basis of previous status will lead to 88% business 
opportunity loss.
- The customers who were previously eligible for loan but did not take it have around 8% default rate which is fine. But
  if we want to further reduce the default rate we should always recalculate the eligibility considering the current situation
  instead of directly passing on the offer in this case

13) Default rate- NAME_CONTRACT_STATUS vs AMT_INCOME_TOTAL

    ![image](https://github.com/devendra2595/Credit_EDA_Assignment/assets/116253033/f229d2c4-ec2a-4132-8288-a8126fa60fad)

* The customers who had loan offer but did not take it previously and currently defaulted the loan have higher avg salary than that of repayers. 
* There is definitly some catch in this case, there is a possibility that bank has offered them the same previous loan offer amount without considering the current situation.

14) Cash Loan Purpose
    
    ![image](https://github.com/devendra2595/Credit_EDA_Assignment/assets/116253033/8e3d9bd6-1468-42fd-b479-9115296a6a3d)

* Cash Loan taken for buying a garage is most likely to be repaid (6% default) where as the customers who refuse to name the purpose of cash loan are most likely to default(23%).


15) Default rate in Goods category
    ![image](https://github.com/devendra2595/Credit_EDA_Assignment/assets/116253033/0a2cabf0-21cb-4fdc-a02c-8db0973abf22)

* Customers who have taken loan for Animals, House Construction, fitness or Tourism are least likely to default around 0 to 4%
* Customers who have taken loan for Vehicle or Insurance are most likely to default around 10%

16) Default rate - Occupation Vs. Contract Status
    ![image](https://github.com/devendra2595/Credit_EDA_Assignment/assets/116253033/0cd4bb8e-74b1-49c9-867b-9689273a288c)

- IT staff have the highest possibility of defaulting if they have taken unused offer loan which is more than 30%.

17) Default rate in Purpose of Cash loan Vs Contarct Status

    ![image](https://github.com/devendra2595/Credit_EDA_Assignment/assets/116253033/64b4058d-f1c5-44fd-9ba3-870dc41dbd5b)

- We can see that the highest possibility of default is in below purpose:
  1) Money for a third person previously refused loan
  2) Payment on the other loans previously given offer
  3) Refusal to name the goal previously approved loan.
  4) Purchase of Electronic equipmets previously cancelled loan.
- We can clearly see that first three are that kind of cases where loan offer should be rejected because the default rate is almost 34%.
- Even in fourth case, we should further drill down to the reason of cancelling the loan and then take decision accordingly.

18) Default rate in Cash Loan Purpose
    ![image](https://github.com/devendra2595/Credit_EDA_Assignment/assets/116253033/7b6bd309-8dff-42b5-a17c-f9282de24bf6)
- Cash Loan taken for buying a garage is most likely to be repaid (6% default) where as the customers who refuse to name the purpose of cash loan are most likely to default(23%).

  
19) Default rate - payment type vs contract status
    ![image](https://github.com/devendra2595/Credit_EDA_Assignment/assets/116253033/1a338c49-52e2-48ce-a1d8-aa946618edf8)

- If  a client wants cashless payment for a previous offer which is still unused, then the the client is 34% likely to default on the loan.

20) Default rate Vs Client type
    ![image](https://github.com/devendra2595/Credit_EDA_Assignment/assets/116253033/0ef3445d-9798-4b7a-a766-2985d083c320)

- New clients are more likely to default than repeat or refreshed clients.

# Recommendations:

- Its better to take extra precaution while approving loans to people with occupation Low-skill Laborers, 
Cooking staff , Drivers, Laborers, Security staff, Waiters/barmen staff
- People from organization type Transport: type 3 , Industry: type 13, Industry: type 8 have higher default 
rate (more than 12%). Need to consider more factor while approving loan or provide loan with higher 
interest rate to mitigate the risk of defaulting.
- In each given contract status, below purpose of loans should be avoided or given with higher interest rate
     - Refused loan- Money for a third person 
     - Unused offer- Payment on the other loans
     - Approved loan- Refusal to name the goal previously.
     - Cancelled loan - Purchase of Electronic equipment.
- If any customer had unused offer, then instead of lending the loan with the same offer, some reworking to be done in the loan offer after a certain period. IT staff is 35% likely to default if they opt for unused offer 
loan.
- It’s better to either avoid lending loan or lend loan at higher interest rate for below categories:
     - Males with Salary range between 900K-1M with Secondary/Secondary special education(~30% default).
     - Females with salary range between 400-500K with Lower secondary education(~50% default)

# Conclusion :

-  Factors which indicates if customer will default or not are:
1. NAME_FAMILY_STATUS : Single people or who have civil marriage have higher default rate.
2. NAME_INCOME_TYPE: Customers who are on Maternity leave or unemployed have higher default rate.
3. NAME_EDUCATION_TYPE: Customers with Lower Secondary & Secondary education have higher default rate.
4. OCCUPATION_TYPE: Low-skill Laborers, Cooking staff , Drivers, Laborers, Security staff, Waiters/barmen staff are 
more likely to default (default rate more than 10%)
5. ORGANIZATION_TYPE: People from Transport: type 3 , Industry: type 13, Industry: type 8 have higher default rate 
(more than 12%) be approved for loan or provide loan with higher interest rate to mitigate the risk of defaulting.
6. DAYS_BIRTH: Very young customers (age group of 20-25) have higher probability of defaulting
7. DAYS_EMPLOYED: Customers with lesser work experience have high default rate.
8. CNT_CHILDREN & CNT_FAM_MEMBERS: More number of family members(similar to more number of children) 
are more likely to default
9. AMT_GOODS_PRICE: When the credit amount goes beyond 3lakhs, there is an increase in defaulters.
10. NAME_GOODS_CATEGORY: Customers who have taken loan for Vehicle or Insurance are most likely to default 
around 10%
11. CASH_LOAN_PURPOSE : Loan taken for buying a garage is most likely to be repaid


- Factors which indicates if customer will repay or not are:
1. CODE_GENDER: Female customers have lesser default rate than male customers (almost 3% lesser)
2. NAME_EDUCATION_TYPE: Customers with Academic degree are less likely to defaults.
3. NAME_INCOME_TYPE: Student and Businessmen have no defaults.
4. ORGANIZATION_TYPE: Customers with Trade Type 4, Industry Type:12 and Transport : Type 1 have defaulted less 
than 5%
5. OCCUPATION_TYPE: Accountants are less likely to default
6. DAYS_BIRTH: People above age of 60 have less probability of defaulting
7. NAME_HOUSING_TYPE : Customers with office apartment are least likely to default
8. DAYS_EMPLOYED: Customers with 25+ year experience(Expert category) are least likely to default
9. AMT_INCOME_TOTAL: Customers with Income more than 700,000 are less likely to default
10. AMT_CREDIT_RANGE : Customers with less than 100K or more than 1M loan amount are less likely to default
11. CNT_FAM_MEMBERS : Customer with 4 or less family members are less likely to default.
12. NAME_GOODS_CATEGORY: Customers who have taken loan for fitness or Tourism are least likely to default around 
4%.
13. CASH_LOAN_PURPOSE : The customers who refuse to name the purpose of loan are most likely to default

