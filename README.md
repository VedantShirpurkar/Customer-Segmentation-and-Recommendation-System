# Customer-Segmentation-and-Recommendation-System
Here's a detailed description of your project for the `.readme` file:

---

# Customer Segmentation and Product Recommendation System

## Overview

This project implements a **Customer Segmentation and Recommendation System** designed to classify customers based on their purchasing behavior and provide personalized product recommendations. It employs advanced machine learning algorithms for segmentation and prediction, alongside an interactive **Streamlit** web application for real-time analysis and recommendations.

The system is capable of processing transaction-level data, performing feature engineering, and generating tailored insights for customer engagement strategies. A random forest classifier powers the recommendation system, ensuring accurate predictions.

## Key Features

1. **Data Cleaning and Transformation**:
   - Handles missing values and duplicate records.
   - Removes negative or zero-valued unit prices and quantities.
   - Derives essential features such as order status, returned quantities, and transaction timelines.

2. **Customer Feature Engineering**:
   - Computes **Recency** (days since the most recent purchase), **Frequency** (number of transactions), and **Monetary Value** (total spending) for each customer.
   - Extracts advanced metrics such as:
     - Total products purchased.
     - Average spending per transaction.
     - Number of unique products purchased.
     - Cancellation rates and total canceled transactions.
   - Calculates the average days between transactions for each customer.

3. **Interactive Streamlit Dashboard**:
   - Users can upload a CSV file containing customer transactional data.
   - Displays processed customer segmentation metrics.
   - Recommends personalized product categories for customers using a trained machine learning model.

4. **Product Recommendation**:
   - Provides top product suggestions based on customer segmentation.
   - Displays product images categorized by predicted class to enhance user experience.

## Workflow

1. **Data Upload**:
   - Users upload a CSV file containing transactional data.
   - Example file structure:
     - Columns: InvoiceNo, StockCode, Description, Quantity, InvoiceDate, UnitPrice, CustomerID, Country.

2. **Feature Engineering**:
   - Data is passed through a custom Python function `feature_eng` that:
     - Performs data cleaning.
     - Derives customer-level metrics.
     - Generates key features for segmentation.

3. **Model Prediction**:
   - The processed customer data is passed to a pre-trained **Random Forest Classifier** (`random_forest_model.pkl`).
   - Predicts the customer class (e.g., High-value, Mid-value, Low-value).

4. **Recommendation Generation**:
   - Based on the predicted customer class, top 5 recommended products are retrieved (`top_5_items.pkl`).
   - Product images from a pre-defined folder structure (`images/Class_X`) are displayed on the dashboard.

5. **Dashboard Display**:
   - Real-time insights, segmentation results, and product recommendations are displayed interactively.

## Example Feature Engineering Outputs

- **Customer Metrics**:
  - `Recency`: Days since the last purchase.
  - `Frequency`: Number of completed transactions.
  - `Monetary Value`: Total spend.
  - `Unique Products Purchased`: Distinct products bought.
  - `Cancellation Rate`: Ratio of canceled transactions to total transactions.

- **Transaction Insights**:
  - Average days between transactions.
  - Total quantity of returned products.
  - Lifetime transaction and spending history.

## Technology Stack

- **Backend**:
  - Python (Pandas, NumPy, Scikit-learn)
  - Feature Engineering Library (`feat_eng.py`)

- **Web Framework**:
  - **Streamlit**: For building an interactive web application.

- **Machine Learning**:
  - Pre-trained **Random Forest Classifier** for customer segmentation and recommendation.

- **Front-end**:
  - Dynamic display of product recommendations with images using Streamlit columns.

## Folder Structure

```plaintext
.
├── app.py                        # Main Streamlit application
├── feat_eng.py                   # Feature engineering functions
├── images/                       # Folder containing product images
│   ├── Class_1/
│   ├── Class_2/
│   ├── Class_3/
├── models/
│   ├── random_forest_model.pkl   # Pre-trained Random Forest Classifier
│   ├── top_5_items.pkl           # Recommended items for each class
└── data/
    └── customer_transactions.csv # Example input data file
```

## Instructions to Run

1. **Install Dependencies**:
   - Install Python packages using `pip install -r requirements.txt`.

2. **Run the Application**:
   - Launch the Streamlit app:
     ```bash
     streamlit run app.py
     ```

3. **Upload Data**:
   - Upload a CSV file in the required format. The app will process the data and display segmentation metrics.

4. **Get Recommendations**:
   - Click on "Recommend Items" to view personalized product suggestions for customers.

## Use Case Scenarios

- **Retail Analytics**:
  - Understand customer purchasing patterns.
  - Optimize product recommendations for targeted marketing.

- **E-Commerce**:
  - Enhance customer experience by delivering personalized shopping suggestions.
  - Reduce churn by identifying high-value customers and offering tailored promotions.

- **Business Decision Making**:
  - Segment customers for better resource allocation.
  - Monitor cancellation and return rates to improve operational efficiency.


