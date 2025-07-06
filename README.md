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
