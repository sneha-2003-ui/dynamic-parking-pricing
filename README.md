# Dynamic Pricing for Urban Parking Lots

## Overview

This project implements a real-time dynamic pricing system for urban parking lots using streaming data. It aims to optimize parking prices based on demand, availability, and temporal factors. The solution simulates live parking data using Pathway and visualizes price changes through an interactive Bokeh dashboard.

The project was developed as part of a capstone program to demonstrate the use of real-time data processing, pricing algorithms, and data visualization in urban mobility solutions.

## Tech Stack
- **Python 3.10+**
- **Pathway** – for stream data simulation and processing
- **Bokeh** – for real-time interactive dashboard visualizations
- **Pandas** – for data manipulation
- **Google Colab** – for notebook execution
- **Panel** – dashboard and layout control

## Architecture Diagram
---
title: Pathway Demand-Sensitive Pricing Pipeline (Model 2)
---
flowchart TD
    A["Load & preprocess CSV data"] --> B["Save stream-ready CSV<br/>with Occupancy, Capacity, QueueLength, IsSpecialDay"]
    B --> C["Simulate data stream<br/>(Pathway replay_csv)"]
    C --> D["Add time columns<br/>(Timestamp, day)"]
    D --> E["Enrich stream:<br/>Occupancy, Capacity, QueueLength,<br/>IsSpecialDay"]
    E --> F["Apply pricing formula:<br/>Dynamic price = f(occupancy,<br/>capacity, queue, special day)"]
    F --> G["Visualize with Bokeh + Panel"]
    G --> H(["User sees demand-sensitive price chart"])

## Project Workflow

1. **Data Loading**  
   Load the parking lot dataset containing timestamped availability and occupancy data.

2. **Preprocessing**  
   Clean, convert and prepare data including timestamp parsing and demand estimation.

3. **Dynamic Pricing Engine**  
   A custom pricing function dynamically updates prices based on current demand vs supply using a linear or exponential model.

4. **Real-Time Simulation with Pathway**  
   Simulates a data stream from the static dataset and processes it in near-real-time.

5. **Bokeh Dashboard**  
   Real-time plots show pricing changes, occupancy, and availability over time.

6. **Output**  
   Dynamic plots and updated price recommendations per lot at each time interval.

    
