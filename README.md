E-Commerce Funnel & Conversion Analysis (Power BI)

##Due to dataset size constraints, the full Power BI file is not publicly shared.
Dashboard screenshots and analytical logic are provided for demonstration purposes.

*Project Objective:

To analyze user behavior data and evaluate performance across the e-commerce conversion funnel:

Visitor → Add to Cart → Purchase

The goal was to identify drop-off points, measure conversion efficiency, and provide data-driven recommendations to improve revenue performance.
Dataset:

The dataset contains session-level event data including:

Event timestamp

Event type (view, cart, purchase)

User session ID

Product price

Brand and category

Large-scale data was cleaned and transformed using Power BI Power Query.

*Key Metrics Created:

1)Distinct Visitors

2)Add to Cart Count

3)Customers (Purchases)

4)View → Cart Conversion %

5)Cart → Purchase Conversion %

6)Overall Conversion %

7)Revenue

8)Drop-off Analysis

*Key Insights:

1)Significant drop-off observed in early funnel stage.

2)Checkout abandonment remains a major revenue leakage point.

3)Revenue is concentrated among select high-performing brands.

4)Conversion performance varies significantly across brands.

*Recommendations:

1)Improve product page experience.

2)Reduce checkout friction.

3)Scale high-converting brands.

4)Optimize underperforming traffic sources.

5)Use retargeting strategies to recover abandoned carts.

Tools Used:

1)Power BI

2)DAX

3)Funnel Modeling

4)KPI Design

5)Data Cleaning & Transformation

*Outcome:

This project demonstrates the practical application of funnel analytics in improving business performance and optimizing marketing strategies.

DAX used for analysis in power bi:
1. Visitors
Visitors =
CALCULATE(
    DISTINCTCOUNT('2019-Nov'[user_session]),
    '2019-Nov'[event_type] = "view"
)

2. Add to Cart
Add_to_Cart =
CALCULATE(
    DISTINCTCOUNT('2019-Nov'[user_session]),
    '2019-Nov'[event_type] = "cart"
)

3. Customers (Purchases)
Customers =
CALCULATE(
    DISTINCTCOUNT('2019-Nov'[user_session]),
    '2019-Nov'[event_type] = "purchase"
)

4)Conversion Rates:

View_to_Cart_% =
DIVIDE([Add_to_Cart], [Visitors], 0)

Cart_to_Purchase_% =
DIVIDE([Customers], [Add_to_Cart], 0)

Overall_Conversion_% =
DIVIDE([Customers], [Visitors], 0)

5)Revenue:

Revenue =
CALCULATE(
    SUM('2019-Nov'[price]),
    '2019-Nov'[event_type] = "purchase"
)

6)Drop-Off Analysis:
Drop_View_to_Cart =
[Visitors] - [Add_to_Cart]

Drop_Cart_to_Purchase =
[Add_to_Cart] - [Customers]
