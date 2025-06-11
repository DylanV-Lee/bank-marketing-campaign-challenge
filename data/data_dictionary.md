# Bank Marketing Dataset – Data Dictionary

## 📘 Main Features

This table provides detailed descriptions of the original features in the Bank Marketing Dataset, as collected by the Portuguese banking institution during its direct marketing campaigns. These features reflect client attributes, contact strategies, and economic indicators used during each campaign.

| Column Name       | Data Type     | Description                                                                                             | Allowed Values / Notes |
|-------------------|---------------|---------------------------------------------------------------------------------------------------------|-------------------------|
| **age**           | Numeric (int) | Age of the client at the time of the campaign.                                                          | Range: 18 to 95         |
| **job**           | Categorical   | The type of job or occupation of the client, used as a socioeconomic segmentation indicator.            | admin., technician, services, blue-collar, retired, unemployed, management, student, entrepreneur, housemaid, self-employed, unknown |
| **marital**       | Categorical   | Marital status of the client.                                                                            | married, single, divorced, unknown |
| **education**     | Categorical   | Highest education level completed by the client.                                                         | basic.4y, basic.6y, basic.9y, high.school, university.degree, professional.course, unknown |
| **default**       | Categorical   | Indicates if the client has credit in default.                                                           | yes, no, unknown        |
| **housing**       | Categorical   | Indicates if the client has a housing loan.                                                              | yes, no, unknown        |
| **loan**          | Categorical   | Indicates if the client has a personal loan.                                                             | yes, no, unknown        |
| **contact**       | Categorical   | Communication type used for contacting the client during the campaign.                                  | cellular, telephone     |
| **month**         | Categorical   | Last contact month of the year when the campaign communication was made.                                | jan, feb, mar, ..., dec |
| **day_of_week**   | Categorical   | Day of the week when the client was last contacted.                                                     | mon, tue, wed, thu, fri |
| **duration**      | Numeric (int) | Duration of the last contact with the client, in seconds. A key factor in campaign success but not known before contact. | Range: 0 to 5000+ seconds |
| **campaign**      | Numeric (int) | Number of contacts performed during the current marketing campaign for this client.                     | Range: 1 to 56          |
| **pdays**         | Numeric (int) | Number of days since the client was last contacted from a previous campaign. 999 means never contacted before. | Range: 0 to 999         |
| **previous**      | Numeric (int) | Number of times the client was contacted in prior campaigns before this one.                            | Range: 0 to 7+          |
| **poutcome**      | Categorical   | Outcome of the previous marketing campaign for this client.                                             | success, failure, nonexistent, unknown |
| **emp.var.rate**  | Numeric (float) | Employment variation rate — a macroeconomic indicator related to the labor market.                      | Range: -3.4 to 1.4      |
| **cons.price.idx**| Numeric (float) | Consumer Price Index — general price level for goods and services.                                       | Range: ~92 to 94        |
| **cons.conf.idx** | Numeric (float) | Consumer Confidence Index — level of consumer trust in the economy.                                     | Range: -50 to -26       |
| **euribor3m**     | Numeric (float) | Euribor 3-month rate — a European benchmark interest rate.                                              | Range: ~0.6 to 5        |
| **nr.employed**   | Numeric (float) | Number of employees — macroeconomic variable indicating employment scale.                               | Range: ~4960 to 5228    |
| **y** (target)    | Categorical   | Indicates whether the client subscribed to a term deposit product. This is the response variable.       | yes, no                 |

## 🧪 Derived Features

The following features were not originally in the dataset but were derived during data analysis to support diagnostic insights and visualization. They were created to aid segmentation, performance comparisons, or summary statistics.

| Derived Feature      | Data Type     | Description                                                                 | Notes / Derivation Logic |
|----------------------|---------------|-----------------------------------------------------------------------------|---------------------------|
| **age_group**        | Categorical   | Age bucketed into labeled segments for easier analysis.                     | Created using bins: young (18–29), adult (30–44), mid-aged (45–59), senior (60+) |
| **contacted_before** | Boolean       | Indicates whether the client was contacted in a previous campaign.          | `True` if `pdays` ≠ 999, else `False` |
| **call_duration_min**| Numeric (float) | Call duration converted from seconds to minutes for interpretation.        | `duration` / 60          |
| **campaign_intensity**| Categorical | Level of outreach based on number of calls in this campaign.                | low (1–2), medium (3–5), high (6+) |

## 🧪 How Derived Features Were Created

This section explains how the additional columns above were constructed to support diagnostic analytics:

- **age_group**: Binned the continuous `age` column into four demographic groups to simplify comparison across life stages.  
- **contacted_before**: A binary transformation of the `pdays` variable — useful for segmenting first-time vs returning contacts.  
- **call_duration_min**: Direct transformation of `duration` into minutes (float) to improve interpretability in business-facing reports.  
- **campaign_intensity**: Categorized `campaign` values into outreach intensity levels — helps assess diminishing returns from repeated calls.