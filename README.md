# Laguna Seca Car Performance Simulator
## IN PROGRESS
A basic car performance simulation engine designed to compare vehicles on the Laguna Seca circuit. The system produces Monte Carlo lap time distributions based on driver skill and car configuration, enabling relative ranking and sensitivity analysis.

## Project Evolution

This project began as a **manual analysis** comparing specific vehicle performance (e.g., Dodge Viper ACR-E vs. Bugatti Veyron Supersport) using static CSV data and Excel-based calculations.

It will evolve into a **scalable, automated engineering project**:
1.  **Ingestion:** Raw car specs and track geometry are loaded via a data pipeline.
2.  **Transformation:** Data is cleaned and standardised using **DuckDB** and **dbt**.
3.  **Simulation:** The core physics engine runs distributed Monte Carlo simulations using **Apache Spark**.
4.  **Deployment:** Results are served via a **FastAPI** web application with real-time visualisation.

## Features

- **Physics-Based Modelling:** Simulates acceleration curves, dynamic downforce, and cornering speeds.
- **Monte Carlo Analysis:** Generates lap time percentiles and confidence intervals.
- **Scalable Architecture:** Designed to handle 10,000+ simulations per car using distributed computing.
- **Generalisation:** Supports adding new cars and tracks via LLM agent or web scraping.

## Tech Stack

| Layer | Technology | Purpose |
| :--- | :--- | :--- |
| **Environment** | **Pixi** | Dependency management (Python 3.11, Java, Spark) |
| **Data Pipeline** | **DuckDB** | Fast, local SQL-based cleaning and staging |
| **Transformation** | **dbt** | Standardising car specs and track segments |
| **Simulation** | **PySpark** | Distributed Monte Carlo processing |
| **Analysis** | **Python** (NumPy, Pandas) | Curve fitting and statistical analysis |
| **Deployment** | **FastAPI** | API for web application and visualisation |


## Planned Project Structure

- **`data/`**: Raw CSV/Excel files for car specs and track geometry.
- **`src/`**: Core simulation engine and physics models.
- **`models/`**: dbt models for data transformation.
- **`output/`**: Generated simulation results and visualisation HTML files.
- **`tests/`**: Unit tests for physics functions and data validation.

## Validation Targets

- **Viper ACR-E:** Target lap time ~1:28.65 (Modelled: ~1:30.65)

