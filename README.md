# Pump-Failure-and-Risk-Analysis

About this project

Goal

This project aims to develop an interactive Power BI dashboard that analyzes and visualizes pump failure risks based on failure modes, locations, and risk severity levels. The dashboard provides valuable insights for the maintenance team, enabling them to prioritize preventive maintenance action.

Data

The dataset consists of pump failure records, categorized by failure types, causes, effects, and maintenance actions. The key data fields include :
- Pump ID & Location : Identifies the affected pump and its operational site.
- Failure Mode : Captures the type of failure, such as cavitation or bearing failure.
- Severity & Likelihood : Quantifies the impact and probability of each failure.
- Risk Matrix : Categorizes failures into different risk levels (High, Moderate, Fair).
- Responsibility & Recommended Actions : Assigns accountability and suggests maintenance actions.
  
Process

1. Data Preparation & Transformation

- Appending Queries
  - Multiple datasets were combined using the Append Queries function in Power BI to consolidate failure data across different time periods.

- Data Segregation
  - The appended data was duplicated and split into Fact and Dimension tables to optimize performance and ensure a structured star schema.
  - Newly created dimension tables, Dim_DateTable and Dim_RiskMatrix were introduced to enhance time-based analysis and risk categorization.
  - The Fact_PumpData table stores key failure-related metrics such as severity, likelihood, and risk score, while dimension tables like Dim_FailureMode, Dim_Pump, Dim_RiskMatrix, and Dim_DateTable provide contextual details for filtering and analysis.

- Data Cleaning
  - Checked for null values and duplicate records to ensure data accuracy.
  - Standardized date formats and failure mode descriptions for consistency across the dataset.

- Calculated Columns
  - Risk Status
  - Risk Score
  - Risk Category
  - Row Header and Column Header
  - Color Formatting

- Calculated Measures
  - Total Pump Count
  -Pump Availability (%)
  - High Risk Count, Moderate Risk Count, Fair Risk Count
  - Under Maintenance Count

2. Data Modeling

A star schema approach was used to structure the data model. The data model was structured using fact and dimension tables, including :

- Fact_PumpData : Stores key risk metrics and pump failure records.
- Dim_Pump : Contains pump location and responsibility details.
- Dim_FailureMode : Details causes, effects, and recommended actions for failure modes.
- Dim_RiskMatrix : Defines the risk categorization logic.
- Dim_DateTable : Enables filtering by time-based analysis (year and quarter).

Relationships were established between these tables, ensuring smooth filtering and drill-down analysis. The Fact_PumpData table connects with all dimension tables using one-to-many relationships to enable effective aggregation.This structure enhances filtering and improves Power BI performance by separating dimensions from the main fact table.

Design

The dashboard includes multiple key visualizations to enhance data understanding :

- Slicers – allows users to filter the dashboard data by year and quarter. Users can select a specific quarter (Q1, Q2, Q3, or Q4) within the same year to analyze trends, risk distribution, and failure patterns over time. This enhances data exploration and drill-down analysis, enabling a focused view of pump performance and maintenance needs for a given period.
  
- Total Pumps – Shows the total number of pumps being monitored.
  
- Under Maintenance – Highlights the number of pumps undergoing maintenance at any given time.
  
- Pumps Availability (%) – Indicates the percentage of pumps currently operational.
  
- Risk Matrix – Maps failure severity vs. likelihood. The Risk Matrix provides a structured approach for the maintenance team to assess pump failures by mapping severity (x-axis) against likelihood (y-axis) using a color-coded heatmap. High-risk failures (red zones) require immediate corrective action to prevent equipment failure and operational disruptions. Moderate risks (yellow zones) are addressed through preventive maintenance to mitigate potential issues. Additionally, the matrix supports long-term predictive maintenance strategies, enabling the team to optimize resource allocation and enhance overall equipment reliability.
  
- Risk Category – Displays the distribution of high, moderate, and fair risks. The Risk Category visual provides a breakdown of pump failures into High, Moderate, and Fair risk levels, allowing the maintenance team to quickly assess the overall risk distribution and focus on addressing high-risk failures first.
  
- Trend Analysis – Tracks risk variations across different quarters. The Risk by Quarter visual helps track fluctuations in risk levels over time, providing insights into emerging failure trends. By analyzing these patterns, maintenance teams can detect operational inefficiencies or increasing failure risks. This insight supports better planning for preventive maintenance, allowing teams to schedule maintenance activities at the right time and minimize unexpected breakdowns, thus improving equipment reliability.
  
- Risk by Location – Highlights areas with frequent failures. The Risk by Location visual highlights the distribution of pump failures across different sites, helping the maintenance team identify high-risk locations that require immediate attention. Since responsibility can be traced based on location, this visual also enables the team to hold the assigned personnel accountable for maintenance actions and ensure prompt corrective measures.

- Risk by Failure Mode – Identifies common failure types affecting pumps. The Risk by Failure Mode visual presents the most common failure types affecting pumps, allowing the maintenance team to identify which failure modes pose the highest risk and require proactive intervention. This analysis helps prioritize maintenance strategies by focusing on the most frequent or severe failure causes, such as bearing failure and cavitation.

- Risk and Failure Table – Provides a detailed view of each failure incident, including corrective actions. The table serves as a comprehensive reference for the maintenance team, allowing them to trace specific failures, identify responsible personnel, and take corrective measures accordingly. By interacting with other visuals, such as Risk by Location and Risk by Failure Mode, users can filter data dynamically to focus on specific problem areas, facilitating a more targeted approach to maintenance planning.

Conclusion

This interactive Power BI dashboard provides a structured risk assessment framework for pump maintenance. By visualizing failure trends and risks, maintenance teams can :
- Prioritize critical failures
- Optimize maintenance schedules
- Reduce unplanned downtime
- Implement predictive maintenance strategies

With a well-defined data model, filtering capabilities, and insightful risk categorization, this dashboard enhances decision-making and supports long-term maintenance planning.
