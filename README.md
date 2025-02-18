# USGS-Earthquake-API-Fabric

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

![Pipeline Architecture](https://prod-files-secure.s3.us-west-2.amazonaws.com/ae89901b-79f1-49d4-828c-c80d4912aeac/f1e7f09e-08ab-4756-b1ed-4341bd68bb8a/Data_Engineering_vs_Software_Engineering_(2).png)

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

![Pipeline Execution Flow](https://prod-files-secure.s3.us-west-2.amazonaws.com/ae89901b-79f1-49d4-828c-c80d4912aeac/a5c115f2-1865-4bb3-a37d-23c527580442/diagram-export-09-12-2024-21_52_01.png)

## Setup Guide

### **Prerequisites**
1. **Microsoft Work Account**: Required for Fabric access.
2. **Microsoft Fabric Account**: Sign up [here](https://app.fabric.microsoft.com/).
3. **Python & PySpark**: Used for data processing.
4. **Power BI**: For visualization and reporting.

### **Step 1: Configure Microsoft Fabric**
- Create a **Fabric Workspace**.
- Set up a **Lakehouse** as the central data repository.

### **Step 2: Fetch Earthquake Data (Stage 1)**
- Use a Python script to extract earthquake data from the **USGS API**.
- Store the data in **Lakehouse Files** as JSON.

### **Step 3: Transform Data (Stage 2)**
- Convert JSON data to structured Delta tables using **PySpark**.
- Standardize fields such as **longitude, latitude, magnitude, and timestamps**.

### **Step 4: Enrich Data (Stage 3)**
- Implement **reverse geocoding** to add country codes.
- Classify earthquakes based on their significance levels.
- Save the final dataset as a Delta table for analysis.

### **Step 5: Visualize in Power BI**
- Load Stage 3 data into **Power BI**.
- Build an **interactive dashboard** with maps, charts, and filters.
- Enable daily **auto-refresh** to keep insights up to date.

### **Step 6: Automate with Data Factory**
- Set up a **Data Factory Pipeline**.
- Automate fetching, transforming, and enriching data.
- Schedule the pipeline to run daily, ensuring real-time updates.

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
