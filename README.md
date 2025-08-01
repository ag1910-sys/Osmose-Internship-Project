# Osmose-Internship-Project
This is A Streamlit app that runs inside Snowflake

# Snowflake streamlit Dashboard
This project is a Streamlit app that runs inside Snowflake. It helps you see how your Snowflake account is being used — including storage, credit usage, and queries — in a clear, interactive way.

# What This Dashboard Does
• Shows how many credits your warehouses are using day-to-day
• Highlights the most expensive queries
• Tracks how your storage is growing over time
• Breaks down where credits are going (compute vs. cloud services)
• Lets you search queries by text, filter by date, and more
• Gives you quick summary stats (total credits, latest storage, etc.)

# What You'll See in the Dashboard
## Daily Credits
• See how many credits your warehouses are using over time
• Filter by date range and warehouse
• Line and bar charts for Visualizations

## Top Costly Queries
• Find the most expensive queries based on credits used
• Use the Top N slider to control how many to show
• Search by keywords in the query text

## Storage Growth
• Track how much storage your account is using
• Shown over time in a simple line chart

## Credit Breakdown
• See how many credits go to compute vs. cloud services
• Helpful for budget planning

## Query Duration
• Histogram of query run times (in seconds)
• Helps spot long-running or inefficient queries

## Summary Stats
• Total credits used
• Average daily credits
• Latest reported storage size

# How to Clone & Run the Repository
If you want to try this dashboard on your own system, here’s how to get started:

## Step 1: Clone the repository
Open your terminal or command prompt, and run:

git clone https://github.com/ag1910-sys/osmose-internship-project.git
This will download a copy of the code into a folder named snowflake-dashboard.

## Step 2: Enter the folder
cd snowflake-dashboard

## Step 3: Install dependencies
Make sure you have Python 3.8+ and pip installed. Then run:

pip install -r requirements.txt
This installs packages like streamlit, pandas, and snowflake-snowpark-python.

## Step 4: Set up Snowflake connection
Inside Streamlit in Snowflake, no extra login is needed — it uses get_active_session().

If you want to run this locally, you’ll need to configure a Snowflake connection using a .env file or connection parameters (not covered here).

## Step 5: Run the app
streamlit run dashboard.py


# How the Data Is Pulled
The app uses simple SQL queries to get data from Snowflake tables (already created under OSM_DEV.RPT).
Example SQL:
## Get warehouse usage:
SELECT * FROM OSM_DEV.RPT.DAILY_WAREHOUSE_CREDITS; 

## Get top credit-consuming queries:
SELECT * FROM OSM_DEV.RPT.TOP_COSTLY_QUERIES; 

## Get storage size over time:
SELECT DATE, TOTAL_STORAGE_USED FROM OSM_DEV.RPT.STORAGE_GROWTH_TABLE;

Don’t worry — the app is wrapped in error handling, so if something goes wrong, you’ll see a helpful message instead of a crash. 

