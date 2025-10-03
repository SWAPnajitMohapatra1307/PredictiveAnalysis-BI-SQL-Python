
# EV Sales Forecasting & Market Strategy Predictive Analysis for an Indian EV Company 

## 📝 Project Summary & Business Impact

This project addresses the high-stakes challenge of strategic market expansion for an Electric Vehicle (EV) manufacturer in the rapidly growing but highly fragmented Indian market. Faced with the risk of multi-million dollar capital misallocation, I moved beyond historical reporting to build a predictive analytics engine.

By cleansing a raw dataset of over **96,000 records** and training a tuned **RandomForest Regressor model**, I generated a granular **11-year sales forecast (2025-2035)**. This forecast serves as the foundation for a data-driven market entry and product strategy, translating complex data into actionable recommendations that directly impact ROI, production efficiency, and risk management.

The final deliverables include not just the predictive model but also a comprehensive **Business Report**,**Powerpoint Presentaion** and an interactive **Power BI Dashboard** designed for executive-level decision-making.

## 📊 Live Power BI Dashboard & Business Report

**Interact with the full analysis and strategic recommendations:**

* **[View the Live Power BI Dashboard]** `[Link to your live Power BI Dashboard]`
* **[Read the Full Business Report]** `[Link to your .docx or .pdf business report]`

**[View the Powerpoint presentaion regarding Sales trend in Goa]** `[Link to your PPt]`

## 🎯 The Business Problem: A High-Risk Expansion
An EV manufacturer is planning expansion in Indian Market but faces significant uncertainty. The market is a complex due to its diverse regional demands, consumer preferences, and seasonal trends. The core business challenge is to move beyond historical analysis and develop a **forward-looking, predictive strategy** to guide investment and operations.

This analysis was designed to answer four critical business questions:

1.  **Market Prioritization:** Which states offer the highest ROI(Return of Investment) for investment in dealerships and marketing?
2.  **Product Mix Optimization:** What vehicle types (e.g., 2W Personal, 3W Shared) will be most in-demand in key regions?
3.  **Risk Mitigation:** Which markets show the slowest adoption trends, indicating a need for a cautious investment strategy?
4.  **Operational Efficiency:** How can we leverage seasonal demand patterns to optimize supply chain and marketing campaigns?

An EV manufacturer needed to define its 5-10 year growth strategy. Investing without data-driven guidance could lead to:
* **Capital Burn:** Sinking millions into dealerships and marketing in low-growth states.
* **Inventory Misalignment:** Producing vehicles that don't match regional demand, leading to high holding costs and lost sales.
* **Inefficient GTM (Go-to-Market):** Launching marketing campaigns during off-peak seasons, resulting in a low ROI(Return of Investment).

My objective was to replace guesswork with a quantitative, predictive framework to guide every strategic decision.


## 💡 Solution & Key Insights 

#### **1. Data Cleaning & Preparation (cleaning_data.ipynb)**

The initial dataset contained **96,895** records with **significant data quality issues**. A rigorous cleaning process was performed in Pandas to ensure the reliability of the analysis.

* **Handled Null & Duplicate Records:** Identified and removed a total of **1,942 records** that were **either null entries or duplicates**. This crucial step reduced the dataset to 94,953 high-quality records for modeling.

* **Corrected Data Types & Formats:** Rectified the data type of the Year column, converting it from float to integer (e.g., 2014.0 to 2014).


* **Standardized Categorical Data:** Cleaned and standardized** 5 key categorical columns (State, Month_Name, Vehicle_Class, etc.)** by **removing leading/trailing whitespaces** and **enforcing consistent capitalization.**

#### **2. Predictive Modeling & Forecasting(Predictive_data_analysis...ipynb)**

With a clean dataset of **94,953 records**, a predictive model was built to forecast future EV sales based on **6 key features (State, Vehicle_Class, Vehicle_Type, Month_Num, etc.).**

**Data Pre-processing with SQL:(Using SQLite library of python)** Initially loaded the data into a SQLite database, using 5 distinct SQL commands (CREATE TABLE, SELECT DISTINCT, UPDATE, etc.) to perform initial deduplication and aggregation.

**Feature Engineering:** Transformed **4 primary categorical features into a machine-readable numerical format** using Scikit-learn's LabelEncoder.

**Model Training & Tuning:** The dataset was split into an **80% training set (approx. 75,962 samples)** and a **20% testing set (approx. 18,991 samples)**.

**A RandomForestRegressor model was trained on 11 years of historical data (2014-2024).**

Model performance was optimized using **GridSearchCV** to systematically test **18 different hyperparameter combinations with 3-fold cross-validation**, identifying the optimal model configuration **(n_estimators: 200, min_samples_split: 2, max_depth: None)**.

**Forecasting:** The final, tuned model was used to generate a granular, **11-year sales forecast (from 2025 to 2035)**. The forecast predicts sales for each specific state, vehicle type, vehicle category, and month, creating millions of future data points for analysis.
#### **3. Insight Generation & Visualization**
The final phase focused on translating the raw forecast data into clear, actionable business intelligence.

Strategic Visualization: Developed **7 distinct strategic visualizations** using Matplotlib and Seaborn to provide direct answers to the core business questions.


#### * 1st **Achievement: Identified Top 5 High-ROI States for Capital Allocation**

* **Methodology:** Aggregated total predicted sales for the 11-year forecast period across **28 states and union territories** to create a data-driven market prioritization matrix.
* **Factual Insight:** The analysis identified **Rajasthan, Uttar Pradesh, Maharashtra, Karnataka, and Bihar** as the Top 5 states for future investment, which together are predicted to account for a significant majority of future sales.
* **Business Impact:** This provides a clear roadmap for where to concentrate capital expenditure on dealerships and marketing to achieve the highest possible return on investment.

![Top 5 States by Predicted Sales](images/top_5_states_chart.png)
*(Note: Replace with your "Top 5 States by Predicted EV Sales" chart)*

#### * 2nd **Achievement: Forecasted Product Mix Demand Across 11 Vehicle Segments**

* **Methodology:** Segmented the sales forecast across **11 distinct vehicle types** to reveal specific consumer preferences within each high-priority state.
* **Factual Insight:** The model reveals significant demand variance. For example, while **Maharashtra** leads in personal two-wheeler sales, **Rajasthan** is the top state for shared three-wheelers (both low-speed and regular).
* **Business Impact:** This enables a demand-driven production strategy, allowing the company to tailor inventory for each state and avoid costly stock imbalances.

![Vehicle Type Breakdown for Top States](images/vehicle_type_breakdown_chart.png)
*(Note: Replace with your "Top 5 States by Predicted EV Sales with Vehicle Type Breakdown" chart)*

#### * 3rd **Achievement: Identified High-Growth Niche Markets**

* **Methodology:** Conducted a deep-dive analysis into the top-performing vehicle categories to identify high-potential states for specific use cases, such as shared mobility and last-mile logistics.
* **Factual Insight:** **Uttar Pradesh** is the definitive market leader for **3W\_Shared\_Lowspeed** vehicles (e-rickshaws), while also showing the highest demand for **3W\_Goods\_Lowspeed**. This highlights its central role in both shared mobility and urban logistics.
* **Business Impact:** These insights allow for targeted, niche marketing and partnership strategies. For example, collaborating with logistics platforms in Uttar Pradesh could rapidly scale the adoption of goods vehicles.
#### * **Interactive Dashboarding (Power BI)** 
An executive-level Power BI dashboard (draft.pbix) was created to provide a dynamic and interactive view of the market forecasts. This allows stakeholders to explore the data and derive insights visually.


* **Key Visualizations:** The dashboard provides at-a-glance views of the top-performing vehicle segments, identifying 3W_Shared_Lowspeed as the overall market leader, followed closely by 2W_Personal vehicles.

**State-Level Deep Dive:** Users can filter by vehicle segment to identify key regional opportunities. 


**Risk & Opportunity Analysis:** The dashboard visualizes both high-growth corridors and lagging markets, identifying states like Mizoram, Meghalaya, and Manipur as low-priority for immediate scalable investment.

#### * **Executive Reporting**
A formal business report (Black Minimalist Indie Publishing Company Financial Report.docx) was compiled to present the findings and outline a clear strategic path forward.


**Primary Strategic Guidance:** The report concludes that the company should focus its primary efforts on the 3W_Shared_Lowspeed and 2W_Personal segments to achieve the most rapid market scaling and impact.


**Secondary Market Capture:** A robust expansion into the 3W_Goods_Lowspeed category is recommended to capture the booming commercial and last-mile logistics market.


**Actionable Recommendations:** The report outlines a three-pronged go-to-market strategy for high-priority states like Uttar Pradesh, Maharashtra, and Karnataka:


**Local Partnerships:** Collaborate with city governments and ride-hailing platforms to launch pilot programs.


**Infrastructure Deployment:** Accelerate the installation of battery-swapping networks to mitigate range anxiety for commercial operators.

**Innovative Financing:** Partner with financial institutions to offer tailored micro-loans and credit lines for fleet owners and entrepreneurs.

#### * **PowerPoint Presentaion**
Created a powerpoint presentaion regarding Analysis of Seasonal EV Sales Trends in Goa which covers:
* Highest Sales Peak
*  Summer Peak 
* Lowest Sales Month
* Steady Sales Period
along with strategic reccomendations 

## 🚀 How to Use

To replicate this analysis, follow these steps:

1.  **Clone the repository:**
    ```sh
    git clone [https://github.com/your-username/your-repo-name.git](https://github.com/your-username/your-repo-name.git)
    ```
2.  **Install dependencies:**
    *(It is recommended to create a `requirements.txt` file)*
    ```sh
    pip install -r requirements.txt
    ```
3.  **Run the Jupyter Notebooks:**
    * First, run `cleaning_data.ipynb` to generate the clean dataset.
    * Then, run `Predictive_data_analysis_using_machine_level_models.ipynb` to perform the analysis.
4.  **Explore the Deliverables:**
    * Open `draft.pbix` in Power BI to interact with the dashboard.
    * Read the `Black Minimalist Indie Publishing Company Financial Report.docx` for the full business case.

---

## 👤 Author

* **[Your Name]**
* **LinkedIn:** `[Your LinkedIn Profile URL]`
* **Email:** `[Your Email Address]`












---
