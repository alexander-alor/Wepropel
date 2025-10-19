# Part 2 – Data Visualization & Insights (Automation Option)

## Objective
Use a Python script to generate summary statistics and simple visualizations from the cleaned, API-enriched dataset, then highlight actionable insights for decision-making.

## Dataset & Tools
- **Dataset:** `merged_with_latest_population.csv`
- **Key columns used:** `Campaign Name`, `Registered`, `Attended`, `Start Date`, `End Date`, `Campaign categories`
- **Libraries:** pandas, matplotlib, seaborn
- **Approach:** Data aggregation with pandas; conditional logic for readable takeaways; tables and charts for quick interpretation.

---

## What I Built
1) **Attendance ratio by campaign**  
   - Grouped by `Campaign Name` to compute registrations vs. actual attendance.  
   - Created a summary table and simple text-based bars (console) to compare campaigns at a glance.

2) **Campaign duration distribution**  
   - Computed `Duration = End Date − Start Date` (inclusive).  
   - Summarized how many rows fall into each duration bucket and saved a bar chart (`duration_vs_rows.png`).

3) **Overall attendance overview**  
   - Compared total `Attended` (value = 1) to the total number of rows to understand the overall attendance ratio across the dataset.  
   - Saved a bar chart of attended vs. not attended (`attended_vs_rows.png`).

---

## Key Insights (with related decisions)

1) **Attendance ratio varies meaningfully by campaign.**  
   - The highest attendance rate appears in **`[Workshop] Eleva tu fundraising con ChatGPT I (2024)`**, while the lowest occurs in **`[Workshop] Crea tu primer GPT (2024)`**.  
   - **Decision this informs:** Prioritize topics that emphasize applied/implementation use-cases (e.g., productivity/fundraising with AI) over beginner-from-zero content when seeking stronger turnout. This also helps identify which campaigns were most successful or most relevant to this audience.

2) **Typical campaign duration and 1-day edge cases.**  
   - Average duration was **about 20 days**. Some campaigns show **1-day** duration because missing dates were filled by assuming start date equals end date (and vice versa), so those rows should be treated with caution.  
   - **Decision this informs:** Use the average duration as a planning baseline for resources (time, budget, and staffing). Treat 1-day entries as incomplete or imputed data and avoid relying on them for resourcing decisions.

3) **Overall attendance level and distribution.**  
   - Comparing total attended vs. total rows yielded an **overall attendance ratio around 50%**, and per-campaign ratios looked proportionate by campaign type.  
   - **Decision this informs:** Use this overall ratio as a rough baseline when forecasting attendance for similar future campaigns and setting conversion expectations by campaign type.

---

## Statistics of Dataset
The first conclusion drawn from the data was the attendance ratio for each particular campaign. This was calculated by counting the number of times the value of ‘Attended’ was 1 (indicating attendance) and dividing it by the number of times the value ‘Registered’ was 1 for each row grouped by the ‘Campaign Name’ column value. The tools used here were the pandas library in Python, along with basic if-else clauses to classify and summarize the results for better understanding. Some insights obtained from this analysis were that the highest attendance rate belonged to the campaign ‘[Workshop] Eleva tu fundraising con ChatGPT’, indicating that most people in the dataset were more involved in the implementation of AI tools rather than learning them from scratch. This conclusion aligns with the fact that the lowest attendance rate belonged to the campaign ‘[Workshop] Crea tu primer GPT’, suggesting little interest in beginner-level content. The dataset involved people who, most of them at least, had advanced knowledge in these topics. This is important for knowing which campaigns were most successful or most relevant to the people in the analysis.

The second relevant conclusion came from the analysis of campaign duration (that is, the End Date minus the Start Date) versus the number of campaigns available in the dataset. To obtain this, a simple subtraction was made to get the number of days a campaign lasted. This is useful to predict the amount of resources that might be needed or reserved for a particular campaign (time, money, etc.). On average, the duration was 20 days, and some had a duration of 1 day due to the filling of information where we had to assume that the Start Date was also the End Date and vice versa, so it would be incorrect to take them as reliable data.

The third and final conclusion was made to have an overall perception of the data. We compared the number of attended (value of 1) versus the number of campaigns (total number of rows). The ratio was 50%, indicating a normal distribution. If we look at the attendance ratio for each particular campaign, we see a proportional distribution by type of campaign as well. These two observations make us think that a normal distribution of attendance is found within this dataset.

The pandas library, along with matplotlib and seaborn libraries, were used to make the charts and tables obtained.

---

## How to Run
1) Place `merged_with_latest_population.csv` in the working directory.  
2) Run the Python script / notebook cells in order.  
3) Outputs:
   - Console tables for:
     - **Attendance by campaign** (including simple text-based bars)
     - **Duration distribution**
     - **Overall attended vs. not attended**
   - Saved charts:
     - `duration_vs_rows.png`
     - `attended_vs_rows.png`

---

## Notes & Assumptions
- Some campaigns show a 1-day duration due to data filling; treat those records as less reliable for duration analysis.  
- Visuals were kept simple and readable to meet the “simple visualizations” requirement.  
- pandas handled the aggregations; matplotlib and seaborn generated the charts.

---

## Files
- `merged_with_latest_population.csv` – input dataset  
- Notebook/script – analysis and visualization code  
- `duration_vs_rows.png`, `attended_vs_rows.png` – exported charts
