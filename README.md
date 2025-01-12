# Evaluating the Impact of Discount Coupon Types on Order Conversion Rates: *A/B Testing with Difference-in-Differences (DiD) Method*
## Background
<p align="justify"> In the competitive world of online business, increasing customer retention and boosting order conversion rates are key objectives for e-commerce businesses. One common strategy to achieve these goals is by offering discount coupons to retain customers who are at risk of leaving, which can be presented in two main forms: fixed amount discounts and percentage-off discounts.</p>

<p align="justify"> This project aims to answer the following question: Which type of discount coupon yields a higher order conversion rate – a <b>50,000 UZS fixed amount discount</b> or a <b>5% off discount</b>? </p>

<p align="justify"> The Marketing Department of an e-commerce platform in Uzbekistan is particularly interested in determining which of these two discount strategies is more effective in driving order conversion rates. To assess this, they have implemented an <b>A/B testing</b> and utilized the <b>Difference-in-Differences (DiD)</b> methodology to measure the impact of the two coupon types while excluding potential confounding variables and underlying trends that could affect the results. </p>

## Test Scenario

### 1. Test Participants (300 in total)
The test involves a total of 300 customers of e-commerce website, divided into two groups:
- **Control group**: 150 customers who did not receive any discount coupons during the testing period.
- **Treatment group**: 150 customers who received one of the two types of discount coupons:
    - *50,000 UZS fixed amount discount* coupon (valid on purchases over 1 million UZS).
    - *5% off discount* coupon (valid on purchases over 1 million UZS, with a maximum discount of 70,000 UZS).

The following table summarizes the setup:

| Group classification |Discount Type                           | Number of Customers |
|--------------------|-----------------------------------------|---------------------|
| Control Group      | No discount                            | 150                  |
| Treatment Group 1  | 50,000 UZS fixed amount discount        | 150                 |
| Treatment Group 2  | 5% off discount coupon (up to 70,000 UZS)| 150                |

### 2. Test Period
<p align="justify"> The A/B test was conducted from *June 5 to June 18, 2024*, with both types of discount coupons being distributed on June 12, 2024. The timeline is as follows:</p>
- June 5–11, 2024: Pre-treatment period
- June 12, 2024: Treatment date (coupon distribution)
- June 12–18, 2024: Post-treatment period

### 3. Hypothesis testing 
*Fixed amount discount* coupon (50,000 UZS) will result in a higher order conversion rate compared to the *5% off discount* coupon.

### 4. Dependent Variable
<p align="justify"> The dependent variable in this study is the **Conversion Rate (CVR)**, defined as the proportion of customers who placed at least one order either before or after the treatment period.</p>

### 5. Independent Variable
The independent variable is the type of discount coupon provided:
- 50,000 UZS fixed amount discount coupon
- 5% off discount coupon

### 6. A/B Testing Evaluation Method – Difference-in-Differences (DiD)
<p align="justify"> The <b> Difference-in-Differences (DiD)</b> method measures the change in order conversion rates for the treatment group before and after the treatment, as well as the change in order conversion rates for the control group over the same period. By comparing these changes, DiD isolates the effect of the other variables which can effect the order conversion rate.</p>

The formula for calculating the DiD is as follows:

**DiD = (𝐴 − 𝑎 ) − (𝐵−𝑏)**

Where:
𝑎 = count of orders in the treatment group before treatment
A = count of orders in the treatment group after treatment
𝑏 = count of orders in the control group before treatment
𝐵 = count of orders in the control group after treatment

**Note**: This analysis focuses on the application of the DiD methodology to the available data, not focusing on population size, sampling methods or data collection procedures for the A/B test itself. 

## About the Dataset

The dataset used for this project consists of two files: *orders.csv* and *coupons.csv*. Below is the metadata for each dataset:

#### **Coupons Dataset**

This dataset contains information about the distribution of discount coupons and includes the following columns:

- **mem_no**: Unique customer ID (primary key), datatype: int.  
- **cpn_nm**: Type of distributed coupon (5% off coupon or 50,000 UZS fixed amount coupon), datatype: varchar(50).  
- **cpn_available_amt**: Minimum purchase amount required to use the coupon (1,000,000 UZS), datatype: varchar(50).  
- **cpn_issued_dt**: The date the coupons were issued (12 June 2024), datatype: varchar(50).  
- **group_class**: Group classification for A/B testing, datatype: varchar(50):  
  - CONTROL: Control group (did not receive any coupons).  
  - TEST1_percent: Treatment group that received a 5% off coupon.  
  - TEST1_fixed: Treatment group that received a 50,000 UZS fixed amount coupon.

**Orders Dataset**

This dataset provides details about customer orders and includes the following columns:

**mem_no**: Customer ID (foreign key), datatype: int.  
**ord_no**: Unique order ID, datatype: int.  
**ord_dt**: Date the order was placed, datatype: varchar(50).

## Tools Used
The data analysis will be conducted using **MySQL** to explore the datasets and perform the A/B test.




## A/B Test Result
The results of the A/B test are summarized in the table below. 

The comparison of the 'before' and 'after' treatment periods reveals the changes in CVR (order conversion rate) over time for each group. Using the DiD method, the 50,000 UZS fixed amount coupon shows an 8% increase in CVR, while the 5% off coupon shows an 11% increase compared to the control group.

Although the 5% off coupon shows a higher increase in CVR compared to the fixed amount coupon, the difference of only 3% between the two treatment groups is too small. Depending on the specific business context and objectives, the initial hypothesis—that the fixed amount discount (50,000 UZS) would result in a higher order conversion rate compared to the 5% off discount coupon—may either be rejected or accepted. 

