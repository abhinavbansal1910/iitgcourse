# carsiitg

CAPSTONE PROJECT 

# 🚗 Dynamic Pricing for Urban Parking Lots

## 📑 Project Overview

Urban parking management is a growing challenge in many cities worldwide. Parking spaces are often limited, and the demand fluctuates significantly throughout the day due to factors such as traffic congestion, special events, time of day, and vehicle types.

Most existing parking systems use static pricing models that do not adapt to these fluctuations, leading to inefficient parking space utilization. During peak times, parking lots may become overcrowded, while at off-peak hours, they may remain underutilized.

This project proposes a dynamic pricing system for urban parking lots that adjusts parking prices in real time based on actual demand and competitor prices. It leverages historical and real-time data to optimize pricing and improve parking space utilization.

The system implements three models:
1. **Model 1 - Baseline Linear Model:** Adjusts price linearly with occupancy.
2. **Model 2 - Demand-Based Model:** Considers multiple demand factors such as queue length, traffic, vehicle type, and special days.
3. **Model 3 - Competition-Aware Model:** Incorporates competitor prices of nearby parking lots for competitive pricing.

---

## ⚙️ Tech Stack Used

| Technology/Library | Purpose |
|--------------------|---------|
| ![Python](https://img.shields.io/badge/Python-3776AB?logo=python&logoColor=white) | Programming Language |
| ![pandas](https://img.shields.io/badge/Pandas-150458?logo=pandas&logoColor=white) | Data Processing & Analysis |
| ![numpy](https://img.shields.io/badge/Numpy-013243?logo=numpy&logoColor=white) | Numerical Computations |
| ![Bokeh](https://img.shields.io/badge/Bokeh-E76F00?logo=bokeh&logoColor=white) | Data Visualization |
| ![Pathway](https://img.shields.io/badge/Pathway-FFD700?logo=streamlit&logoColor=white) | Real-Time Data Streaming (Local) |
| ![Google Colab](https://img.shields.io/badge/Google%20Colab-F9AB00?logo=googlecolab&logoColor=white) | Development Environment |

---

## 📊 Architecture Diagram

```mermaid
flowchart TD
    A[CSV Dataset (Parking Data)] --> B[Preprocessing (pandas & numpy)]
    B --> C[Pricing Models (Model 1, 2, 3)]
    C --> D[Bokeh Visualizations]
    C --> E[Pathway Real-time Streaming (Local Use Only)]


🔍 Detailed Project Architecture & Workflow
Step 1: Data Loading & Preprocessing
Load historical parking data in CSV format.

Data includes occupancy, vehicle types, queue lengths, traffic conditions, and time-based features.

Filter records for specific parking lots and sort data to simulate time-series streaming.

Step 2: Model Development
Model 1: Baseline Linear Model
Adjusts price proportionally to occupancy ratio:

Price_t+1 = Price_t + alpha × (Occupancy / Capacity)
Model 2: Demand-Based Model
Factors in multiple demand indicators:


Demand = alpha × (Occupancy / Capacity) + beta × QueueLength - gamma × Traffic + delta × SpecialDay + epsilon × VehicleTypeWeight
Price_t = BasePrice × (1 + lambda × NormalizedDemand)
Demand is normalized, and prices are bounded between 0.5× and 2× of the base price.

Model 3: Competition-Aware Model
Analyzes competitor pricing in nearby parking lots.

Uses Haversine formula for distance computation.

Pricing logic:

If nearby lots are cheaper and availability is high, prices are reduced or rerouting is suggested.

If nearby lots are expensive, prices may increase slightly but stay within defined bounds.

Step 3: Visualization
Bokeh library is used to create interactive plots showing price evolution for all models across time.

Step 4: Real-Time Streaming Simulation (Pathway)
The Pathway framework enables continuous price adjustments based on incoming data.

Works only on local systems due to file system constraints in Colab.

📄 Additional Documentation
Full project report: Capstone_Project_Report.pdf

Colab Notebook containing all code, models, and visualizations.

Model explanations, assumptions, and formulae are included in the report.

🚀 Future Enhancements
Incorporate live traffic APIs for even more dynamic pricing.

Use reinforcement learning to optimize prices over longer horizons.

Expand the system to multiple cities with regional pricing differences.

Deploy the system as a full cloud-based microservice with a front-end dashboard.
