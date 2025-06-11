# Bank Marketing Dataset – README

### 📊 Data Overview – Bank Marketing Dataset (Portugal)

This dataset contains customer-level data collected from a Portuguese bank’s marketing campaign. It includes information about clients, their financial and personal background, and responses to phone-based marketing calls. The data was collected over multiple direct marketing campaigns between 2008 and 2013.

The dataset was released as part of a public repository by the University of California, Irvine (UCI), and is widely used for benchmarking marketing and classification tasks.

### 🗂️ Dataset Summary
- **Source**: UCI Machine Learning Repository  
- **Time Range**: 2008–2013 (over multiple campaigns)  
- **Rows**: 45,211  
- **Columns**: 17 features + 1 target variable  
- **Domain**: Banking, Marketing Campaign Analytics  

### 🧠 Project Usage

This dataset was analyzed to:
- Understand marketing campaign efficiency
- Evaluate client response by demographic and economic segments
- Identify causes of campaign failure and wasted effort
- Support business strategy with descriptive and diagnostic insights

### 🎯 Target Variable

This is **not** primarily a predictive modeling project. However, the variable `y` indicates whether the client subscribed to a term deposit (`yes`/`no`). It is used in analysis to study which factors influenced campaign success.

### 🔍 Missing Data

There are **no missing values** in this dataset. All fields are populated, but some placeholder values (e.g., `"unknown"`) exist and need careful interpretation during analysis.

### 📄 Data Dictionary

For a complete description of each feature in the dataset, including data types and allowed values, refer to the [Data Dictionary](./data_dictionary.md).