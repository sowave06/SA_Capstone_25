README: Dynamic Pricing for Urban Parking Lots — Capstone Project (Summer Analytics 2025)
Project Overview
This project implements a real-time, data-driven dynamic pricing engine for 14 urban parking spaces, using historical and live data streams. The goal is to optimize parking lot utilization and revenue by adjusting prices based on demand, competition, and real-time conditions.

Key Features:

Real-time price updates for each parking lot

Multiple pricing models (baseline, demand-based, competitive)

Data visualization with Bokeh

Code written from scratch using Python, Pandas, and Numpy

Table of Contents
Background & Motivation

Dataset Description

Project Structure

How to Run

Pricing Model Details

Assumptions

Visualization

Key Files

Contact

Background & Motivation
Urban parking is a scarce resource. Static pricing leads to inefficiencies such as overcrowding or underutilization. Dynamic pricing, informed by real-time demand and competition, can improve both utilization and user experience.

Dataset Description
Data Source: 14 parking spaces, 73 days, 18 time points/day

Features:

Location: Latitude, Longitude

Lot Features: Capacity, Occupancy, Queue Length

Vehicle: Type (car, bike, truck)

Environment: Traffic Level, Special Day Indicator

Objective: Use these features to set and update parking prices in real-time

Project Structure
text
.
├── SA_Cap_25.ipynb        # Main Jupyter notebook (code + visualizations)
├── problem-statement.pdf  # Official project brief
├── dataset.csv            # Parking lot data (if provided)
├── README.md              # This file
How to Run
Environment:

Google Colab (recommended)

Python 3.x

Required libraries: numpy, pandas, bokeh, pathway

Steps:

Open SA_Cap_25.ipynb in Google Colab.

Run all cells sequentially.

The notebook will:

Ingest and process the dataset

Simulate real-time data streaming

Apply pricing logic (all models)

Display real-time Bokeh visualizations

Pricing Model Details
Model 1: Baseline Linear Model
Price increases linearly as occupancy rises.

Formula:
Price_t+1 = Price_t + α * (Occupancy / Capacity)

Model 2: Demand-Based Function
Price is a function of normalized demand, which includes:

Occupancy rate

Queue length

Traffic level

Special day indicator

Vehicle type

Formula:
Demand = α*(Occupancy/Capacity) + β*Queue + γ*Traffic + δ*SpecialDay + ε*VehicleType
Price_t = BasePrice * (1 + λ * NormalizedDemand)

Price is bounded (0.5x to 2x base price).

Model 3: Competitive Pricing (Optional)
Considers competitor prices and proximity.

Adjusts price if nearby lots are cheaper or more expensive.

Suggests rerouting if lot is full and nearby lots are available.

Assumptions
All models are implemented from scratch (no ML libraries except numpy/pandas).

Base price for all lots starts at $10.

Price changes are smooth and explainable.

Demand normalization ensures stability.

Real-time simulation is handled via Pathway.

Visualization
Bokeh is used for real-time price line plots for each parking space.

Comparative plots show pricing trends across lots and versus competitors.

Visuals justify pricing behavior and model decisions.
