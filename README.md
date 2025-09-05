 GTC ML Project 1 - Hotel Bookings

The goal of this project is to prepare hotel booking data so it can be used later to build a model that predicts if a booking will be canceled or not.  

I focused on cleaning and preprocessing the data step by step.  

Steps   

1- Exploratory Data Analysis (EDA)  
- Checked basic info and summary stats (info and describe).  
- Looked at missing values and plotted a heatmap.  
- Plotted boxplots for `adr` and `lead_time` to detect outliers.  
- Counted outliers using the IQR method.  

 2- Data Cleaning  
- Filled missing values:  
  - company and agent → replaced with 0  
  - country → filled with the mode (most frequent)  
  - children → filled with the median  
- Removed duplicate rows.  
- Fixed outliers in `adr` by capping values at 1000.  
- Dropped rows where adults = 0.  
- Converted `reservation_status_date` to datetime format.  

3- Feature Engineering  
- Created new columns:  
  - total_guests = adults + children + babies  
  - total_nights = stays_in_weekend_nights + stays_in_week_nights  
  - is_family = 1 if children or babies > 0 else 0  
- Dropped columns that cause data leakage like `reservation_status` and `reservation_status_date`.  
- Applied one-hot encoding for categorical features like meal, hotel, market_segment.  
- For country, used frequency encoding.  

 4- Train/Test Split  
- Split the data into training (80%) and testing (20%) using train_test_split.  

Files  
- hotel_bookings.csv → original dataset  
- project_notebook.ipynb → notebook with all steps  
- cleaned_hotel_bookings.csv → cleaned dataset (optional)  
- README.md → this file  

 How to Run  
- Open the notebook in Google Colab or Jupyter.  
- Upload the dataset file (hotel_bookings.csv).  
- Run all the cells in order.  
