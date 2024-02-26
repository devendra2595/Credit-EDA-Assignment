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

