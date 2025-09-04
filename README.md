# Netflix and Prime Content Data Analysis

**Screenshot:**  
<p align="center">
<img width="300" alt="Screenshot 2025-03-12 at 12 36 08 PM" src="https://github.com/user-attachments/assets/c69f4361-bde9-44fe-82f0-e222f3773d95" />
<img width="300" alt="Screenshot 2025-03-12 at 12 36 24 PM" src="https://github.com/user-attachments/assets/623ba67f-0ad6-4fee-9269-4bfcb94c3dfc" />
<img width="300" alt="Screenshot 2025-03-12 at 12 36 42 PM" src="https://github.com/user-attachments/assets/74ca6e95-e904-4c2c-879e-9854bf37df76" />
</p>

This project analyzes the content available on **Netflix** and **Amazon Prime Video** using data obtained from Kaggle. The goal was to explore the platforms’ libraries, compare their content, and visualize insights through interactive dashboards.  

## 📊 Dataset  
The datasets were sourced from Kaggle:  
- [Netflix Shows Dataset](http://kaggle.com/datasets/shivamb/netflix-shows)  
- [Amazon Prime Movies and TV Shows Dataset](https://www.kaggle.com/datasets/shivamb/amazon-prime-movies-and-tv-shows)  

Each dataset contains metadata such as:  
- Title  
- Type (Movie / TV Show)  
- Genre  
- Release year  
- Country of origin  
- Ratings  
- Directors & Cast  

## Project Workflow  
1. **Data Collection**  
   - Downloaded datasets from Kaggle.  

2. **Data Cleaning (CSV level)**  
   - Removed duplicates and missing values.  
   - Standardized columns for joining datasets later.  

3. **Exploratory Data Analysis (EDA) – Python in Google Colab**  
   Example analyses done in Python before moving to Power BI:  

   ```python
   # Load the data
   import pandas as pd

   netflix = pd.read_csv("netflix_titles.csv")
   prime = pd.read_csv("amazon_prime_titles.csv")

   netflix.shape, prime.shape
   ```

   ```python
   # Missing value check
   netflix.isnull().sum().sort_values(ascending=False).head(10)
   ```

   ```python
   # Count shows by type on both platforms
   netflix['type'].value_counts()
   prime['type'].value_counts()
   ```

   ```python
   # Distribution of Netflix content by release year
   import matplotlib.pyplot as plt
   import seaborn as sns

   plt.figure(figsize=(10,5))
   sns.histplot(netflix['release_year'], bins=40, color="red", kde=False)
   plt.title("Netflix Shows by Release Year")
   plt.show()
   ```
<img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/c5ae24e4-af56-418c-a974-b3d5e8d5cc3b" />
<img width="500" height="500" alt="image" src="https://github.com/user-attachments/assets/25069574-91d9-4f03-974b-063c61957224" />

   📓 The full notebook is available here: `eda_netlfix_prime_showdata.ipynb`  

4. **Data Transformation & Visualization (Power BI)**  
   - Additional cleaning and transformations in **Power Query**.  
   - Created calculated fields for analysis.  
   - Designed **3 Dashboards**:  
     - **Netflix Dashboard**  
     - **Prime Video Dashboard**  
     - **Comparison Dashboard**  

## 📈 Dashboards  

### 🔴 Netflix Dashboard  
- Total shows, genres, directors, and countries.  
- TV vs. Movies distribution.  
- Ratings breakdown.  
- Trends by release year.  
- Country-wise availability.  

### 🔵 Prime Video Dashboard  
- Total shows, genres, directors, and countries.  
- Movies vs. TV Shows split.  
- Trends by release year.  
- Country-wise availability.  
- Top contributing directors.  

### ⚖️ Comparison Dashboard  
- Overlap in show counts between Netflix & Prime.  
- Side-by-side analysis of genres, release years, and ratings.  
- Insights into global reach of both platforms.  

![Comparison Dashboard](Screenshot%202025-09-04%20at%203.37.02 PM.png)  

## 🚀 Tech Stack  
- **Python (Google Colab)** – Data Cleaning & EDA  
- **Pandas, Matplotlib, Seaborn** – Analysis & Visualizations  
- **Power BI** – Final Dashboards & Insights  

## 📂 Repository Structure  
```
├── eda_netlfix_prime_showdata.ipynb   # EDA notebook in Python
├── data/                              # Cleaned CSV files (optional if added)
├── dashboards/                        # Power BI reports (optional if added)
├── plots/                             # Exported plots from EDA
├── README.md                          # Project documentation
```

## 🔮 Key Insights  
- Netflix has a larger number of shows overall compared to Prime.  
- Prime Video has more directors listed but fewer genres.  
- Netflix has broader international coverage.  
- Genre preferences differ across platforms (Netflix favors International TV, Prime favors Documentaries & Drama).  

## 📌 Future Work  
- Extend analysis with **Disney+ and Hulu** datasets.  
- Perform **sentiment analysis** on user reviews (if available).  
- Automate ETL pipeline for periodic updates.  
