# Retail Supply Chain Optimization: Maximizing Daily Profit 🚛📦

![Status](https://img.shields.io/badge/Status-Validated-success)
![Tech](https://img.shields.io/badge/Stack-Python_|_AMPL_|_Gurobi-red)
![Focus](https://img.shields.io/badge/Focus-Operations_Research_|_Logistics-blue)

## Executive Summary
**The Challenge:** A retail chain needed to optimize its expansion strategy, facing a complex set of decisions: which warehouses to open, which stores to stock, how to price items, and how to route delivery trucks—all while maximizing daily profit.
**The Constraint:** Solving this as a single mathematical model was computationally intractable due to the massive decision space.

**The Solution:** We developed a **Decomposition-Based Optimization Framework**. We broke the problem into logical sub-components (Warehouse Selection, Pricing, Routing) and solved them using a hybrid of **AMPL (Linear Programming)** and **Heuristic Algorithms**.

**Key Impact:**
* **Profit Maximization:** Achieved a daily profit of **$56,811**, significantly outperforming the baseline ($48,000) and exceeding the project target by a wide margin.
* **Optimization Efficiency:** Successfully balanced warehouse rent costs against transportation times, selecting Warehouses 3, 4, 6, and 7 for optimal coverage.
* **Validation:** The solution was rigorously tested against a feasibility checker (`solution_validator.ipynb`) to ensure all routing and capacity constraints were met.

---

## Methodology: The Decomposition Approach

### 1. Strategic Planning (AMPL/Gurobi)
We used Linear Programming to make high-level capital decisions:
* **Warehouse Selection:** Selected 4 optimal locations to minimize rent while maximizing reach.
* **Uniform Pricing:** Implemented a pricing strategy that balanced demand generation with travel-based price constraints.

### 2. Operational Routing (Heuristics)
Once locations were fixed, we used Python to solve the Vehicle Routing Problem (VRP):
* **Clustering:** Grouped stores based on proximity to selected warehouses.
* **Route Construction:** Built efficient delivery routes that satisfied vehicle capacity and time limits.

### 3. Validation
We built a custom validator (`solution_validator.ipynb`) to verify the feasibility of our routes and financial projections.
* *Result:* 0 constraint violations. Profit verified at $56,811.

---

## How to Run the Solution
This repository includes the solution code and a validator script.

1.  **Run the Optimization:**
    Open `optimization_solver.ipynb` to see the AMPL/Python logic that generates the strategy.

2.  **Validate the Results:**
    Open `solution_validator.ipynb` and ensure the following data files are present:
    * `routes.txt`
    * `stores.txt`
    * `warehouses.txt`
    
    *Run the notebook to see the "Feasible Solution" output and profit calculation.*

---
*This project was conducted as part of the BUDT732: Decision Analytics course at the University of Maryland.*
