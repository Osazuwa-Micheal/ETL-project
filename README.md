#  Data Extraction, Cleaning, and Saving

This project focuses on the **extraction, cleaning, and storage** of raw data files to ensure data quality, consistency, and accessibility for further analysis.  
The dataset originates from a collection of files related to **bicycle store operations**, including information on **orders, customers, products, stores, and staff**.

---

##  Project Overview
The goal of this project is to:
- Extract raw data from multiple files within a compressed archive stored in Google drive.
- Clean and standardize the data by handling missing values and inconsistencies.
- Save the cleaned data in **CSV** and **SQL database** formats for easy access and integration with analytical tools.

---

## 1️⃣ Data Extraction
The extraction process involved:
- Accessing the specified archive folder:  
- Loading the first **9 files** into separate pandas DataFrames (`df1` through `df9`).
- Assigning descriptive names to the DataFrames:
- `order_items`
- `customers`
- `stores`
- `stocks`
- `brands`
- `orders`
- `products`
- `staffs`
- `categories`

---

## 2️⃣ Data Cleaning
Cleaning procedures were applied to ensure data integrity:

### **orders** DataFrame
- Converted date columns to `datetime` objects.
- Handled missing values in the `shipped_date` column using **forward fill** (`ffill`).

### **customers** DataFrame
- Stripped leading and trailing whitespace from string columns:
- `first_name`, `last_name`, `phone`, `email`, `street`, `city`, `state`
- Dropped columns with excessive missing values:
- `phone` column removed.

### **staffs** DataFrame
- Filled missing values in the `manager_id` column:
- Used a placeholder value `0` (alternative: filling with the mode).

### Other DataFrames
- `order_items`, `stores`, `stocks`, `brands`, `products`, and `categories`  
- Inspected and found to have **no significant issues** requiring cleaning.

---

## 3️⃣ Data Saving
The cleaned DataFrames were saved in **two formats** for maximum usability:

### CSV Files
- A new directory named **`cleaned_data`** was created.
- Each DataFrame was saved as a separate CSV file, e.g.:
- `customers.csv`
- `orders.csv`
- `products.csv`
- … and others.

### SQL Database
- All cleaned DataFrames were saved as tables in a **SQLite database**:
- Database name: `cleaned_data.db`
- Each DataFrame became a table with the **same name** inside the database.

---

## 🛠️ Technologies Used
- **Python** (Pandas, SQLite3)
- **Google Colab** for notebook-based development
- **SQLite** for database storage

---

