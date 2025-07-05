# SummerAnalytics25
A data-driven, real-time dynamic pricing engine for urban parking lots. 

*Dynamic Pricing for Urban Parking Lots*

**Overview:**

This project implements a real-time, data-driven dynamic pricing engine for urban parking lots. Using only the provided dataset, the system adjusts parking prices in response to real-time demand, congestion, special events, and competitor pricing. The solution is fully reproducible, modular, and designed for transparency, with interactive visualizations and comprehensive documentation.

**Tech Stack:**

Python: Core programming language

pandas & numpy: Data manipulation and feature engineering

Pathway: Real-time data streaming and simulation

Bokeh: Interactive visualizations in Jupyter/Colab

Jupyter/Google Colab: Development and demonstration environment

scipy: Spatial analysis for competitor identification

Mermaid: Architecture diagramming

**Architecture Diagram:**

flowchart TD
    A[dataset.csv] --> B[Pathway Streaming]
    B --> C[Feature Engineering (pandas/numpy)]
    C --> D[Pricing Models]
    D --> E[Real-Time Price Output]
    E --> F[Bokeh Visualizations]
    D --> G[Competitor Price Analysis]
    G --> F
    
**Project Architecture & Workflow:**

1. Data Ingestion
Source: dataset.csv containing 18,000+ records of 14 parking lots over 73 days.

Streaming: Pathway simulates real-time data ingestion, replaying records in timestamp order to mimic live data streams.

2. Feature Engineering
Occupancy Rate: Calculated as Occupancy / Capacity.

Vehicle Type Weighting: Assigns weights to vehicle types (e.g., truck > car > bike > cycle) to reflect willingness to pay.

Traffic & Event Encoding: Converts traffic conditions and special day indicators into numeric features for modeling.

3. Pricing Models
Baseline Linear Model: Price increases linearly with occupancy rate.

Demand-Based Model: Price is a function of normalized demand, incorporating occupancy, queue length, traffic, special events, and vehicle type.

Competitive Pricing Model: Adjusts prices based on the average price of the three geographically closest competitor lots.

4. Real-Time Prediction Output
As new data arrives, the system processes features and emits updated price predictions for each lot in real time.

5. Visualization
Bokeh is used to create interactive, real-time plots:

Pricing evolution for each lot (demand-based vs. linear)

Competitor price comparisons

Demand and queue visualizations
