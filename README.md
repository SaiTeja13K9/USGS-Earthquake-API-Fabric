# Earthquake Data Pipeline Using Microsoft Fabric

## Overview
This project provides a step-by-step guide to building an automated data pipeline using **Microsoft Fabric** to process and visualize earthquake data. The pipeline follows a **structured multi-stage architecture** (Stage 1, Stage 2, Stage 3) to ensure raw data is ingested, transformed, and enriched for high-quality insights. The final output is visualized using **Power BI**, offering real-time insights for decision-making.

## Business Case

Accurate earthquake data is crucial for disaster response agencies, researchers, and insurance companies. This project enables automated data collection and processing, providing stakeholders with up-to-date and structured information for effective analysis and decision-making.

## Solution Workflow

The earthquake data pipeline consists of the following stages:

1. **Stage 1 (Raw Data Ingestion)**: Collects earthquake data from an external API and stores it in the **Fabric Lakehouse**.
2. **Stage 2 (Data Transformation)**: Cleans and structures the data by converting JSON files into Delta tables with meaningful columns.
3. **Stage 3 (Data Enrichment)**: Enhances the data with additional features such as country codes and significance classifications.
4. **Power BI Dashboard**: Provides an interactive visualization for trend analysis and insights.
5. **Data Factory Automation**: Ensures data is updated daily, eliminating manual intervention.


## Power BI Visualizations

### **Bubble Map (Point Map)**

![image](https://github.com/user-attachments/assets/b3b6eb22-52e4-4f3f-a9f0-ebdcc4c96dfe)


- This map visualizes individual earthquake occurrences using latitude and longitude.
- **Bubble size** represents the sum of earthquake significance.
- **Color coding** differentiates between high, moderate, and low significance earthquakes.
- This visualization helps in identifying seismic hotspots worldwide.

### **Filled Map (Choropleth Map)**

![image](https://github.com/user-attachments/assets/09dbfc54-b5e2-455b-ba6b-6a9a5103c567)


- This map shades entire countries based on the total earthquake significance.
- **Darker shades** indicate regions with higher seismic activity.
- Helps in understanding seismic trends at a **country-wide level** rather than individual events.
- Useful for policymakers and disaster management teams.

## Technical Implementation

### **Stage 1: Raw Data Ingestion**
- Fetches earthquake data from the USGS API.
- Stores raw JSON files in the **Fabric Lakehouse**.
- Ensures data integrity for future audit purposes.

### **Stage 2: Data Transformation**
- Converts raw JSON data into structured **Delta tables**.
- Extracts key attributes such as **event time, magnitude, and location**.
- Removes inconsistencies and formats timestamps for analysis.

### **Stage 3: Data Enrichment**
- Uses **reverse geocoding** to add country codes to earthquake locations.
- Classifies earthquakes based on their significance levels.
- Optimizes the dataset for advanced analytical queries.

### **Power BI Visualization**
- Loads **Stage 3** data into **Power BI**.
- Displays earthquake trends, severity, and geographical distribution.
- Enhances accessibility of insights through an interactive dashboard.

### **Data Factory Orchestration**
- Automates data collection, transformation, and enrichment processes.
- Runs the pipeline daily, ensuring the latest data is always available.
- Uses **Microsoft Fabric Data Factory** to schedule and monitor workflows.

![image](https://github.com/user-attachments/assets/ef978755-6a75-4136-832c-5074bc8564c1)


## Summary

This project showcases the capabilities of **Microsoft Fabric** in handling real-world data engineering challenges. By following a structured pipeline, raw earthquake data is transformed into actionable insights that aid in risk assessment and disaster preparedness. The use of **automated orchestration** ensures seamless daily updates, eliminating manual efforts and enhancing data reliability.

---

### **Next Steps**
- Expand the dataset to include **historical earthquake trends**.
- Integrate **machine learning models** for earthquake risk prediction.
- Implement **real-time alerting** for high-magnitude events.

---

### **References**
- [Microsoft Fabric Documentation](https://learn.microsoft.com/en-us/fabric/)
- [USGS Earthquake API](https://earthquake.usgs.gov/fdsnws/event/1/)
- [Power BI Guides](https://learn.microsoft.com/en-us/power-bi/)
