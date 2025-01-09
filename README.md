# Hotel Revenue Management Optimization

This repository contains a comprehensive implementation of a hotel revenue management optimization project. The objective was to maximize revenue by determining optimal static and dynamic allocation policies for room reservations using probabilistic demand modeling and optimization techniques.

## Project Overview
This project focuses on optimizing revenue for a luxury hotel offering three types of rooms (Queen, King, and California King) over a specific 8-day period. By leveraging probabilistic data on customer booking behavior, pricing structures, and room availability, optimal static and dynamic policies were developed to allocate room reservations effectively.

The dynamic allocation policy, implemented using Gurobi, achieved a significant monthly revenue increase of approximately **$164,000**, compared to a baseline first-come, first-serve policy.

## Key Features
**Probabilistic Demand Modeling:** Modeled customer requests for room reservations based on probabilistic data from historical booking patterns.

**Static Allocation Policy:** Formulated and solved a linear programming (LP) model to determine optimal room allocation over a 90-day horizon.

**Dynamic Allocation Policy:** Designed and implemented a dynamic decision-making framework using bid-price controls and LP-based optimization to maximize revenue in real-time.

**Simulation Analysis:** Conducted Monte Carlo simulations with 100 random request sequences to evaluate and compare revenue outcomes of different policies.

## Methodology
**1. Data Analysis:**

• Processed and analyzed the probability of customer requests for specific room types and booking periods using pandas and numpy.

• Derived expected demand, room constraints, and revenue structures.

**2. Static Allocation:**

• Formulated an LP model with:

  • Decision Variables: Number of accepted requests for each combination of room type and booking period.

  • Constraints: Room availability limits across days and room types.

  • Objective Function: Maximization of total revenue based on pricing and demand.

• Solved the LP using Gurobi to determine the optimal allocation policy.

**3. Dynamic Allocation:**

• Simulated real-time requests over 540 periods (90 days × 6 periods/day).

• Implemented a bid-price control mechanism:

  • Computed opportunity costs using dual variables from the static LP.
  
  • Accepted requests only if incremental revenue exceeded bid-price costs.
  
• Evaluated performance over 100 simulations.

## 4. Technologies Used

• **Python Libraries:**

  • pandas, numpy for data manipulation and analysis.

  • gurobipy for optimization modeling and solving.

• **Optimization Solver:** Gurobi.

• **Monte Carlo Simulation:** NumPy random sampling for request generation.

## 5. Results

**Static Allocation:**

• Solved an LP model to determine the optimal allocation of room requests over 90 days, yielding maximum revenue.

**Dynamic Allocation:**

• Implemented a bid-price control mechanism that increased monthly revenue by $164,000 compared to a first-come, first-serve policy.

**Simulation Insights:**

• Analyzed 100 random request sequences to validate the robustness of the dynamic allocation policy.
