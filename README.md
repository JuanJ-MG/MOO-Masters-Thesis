# AM-vs-TM-MOO-Masters-Thesis


# NOTEBOOK NAVIGATION GUIDE

This notebook implements and analyzes multiple optimization models comparing
Additive Manufacturing (AM) and Traditional Manufacturing (TM) under cost,
time, and uncertainty considerations.

The notebook is organized by MODEL TYPE and SCENARIO.
Each section is self-contained but follows a logical progression.
Running the notebook top-to-bottom is recommended.


#### Section 1: Incremental Discounts Model (Piecewise Linear Costs)

This section implements Model 1, where economies of scale are represented using piecewise linear (incremental) cost functions.

1.1 Incremental Discounts with Capacity Constraints
	•	Baseline MILP formulation
	•	Includes:
	•	Demand satisfaction
	•	Budget constraint
	•	Machine capacity constraints
	•	No lead time effects
	•	Serves as the reference model

1.2 Incremental Discounts – No Lead Time
	•	Assumes machines can start production immediately
	•	Generates Pareto frontiers across different demand levels
	•	Used to study pure cost–time tradeoffs

1.3 Incremental Discounts – With Lead Time
	•	Adds fixed startup delays for each technology
	•	Penalizes TM casting due to long tooling lead times
	•	Shows how tighter deadlines shift optimal solutions toward AM

1.4 Incremental Discounts – 30% AM Setup Cost Reduction
	•	Applies a 30% reduction to AM fixed setup costs
	•	Re-solves the lead-time model
	•	Evaluates whether lower capital cost alone improves AM competitiveness

⸻

#### Section 2: Bulk Discount Model (Binary Bracket Formulation)

This section implements Model 2, where economies of scale are modeled using binary pricing brackets instead of continuous PWL functions.

2.1 Bulk Discounts – No Lead Time
	•	Uses binary variables to activate volume-based pricing tiers
	•	No lead time penalties
	•	Enables direct comparison with incremental discount results

2.2 Bulk Discounts – With Lead Time
	•	Adds technology-specific lead times
	•	Highlights differences between AM and TM under realistic startup delays

2.3 Bulk Discounts – Lead Time with 30% AM Setup Cost Reduction
	•	Applies the same AM cost reduction under the bulk discount structure
	•	Confirms that capacity and lead time, not setup cost alone, drive dominance

⸻

#### Section 3: Monte Carlo Simulation

This section introduces uncertainty into the optimization framework.
	•	Repeats the optimization thousands of times
	•	Randomly samples:
	•	Demand
	•	Time limits (ε)
	•	Setup costs
	•	Unit costs
	•	Processing times
	•	Machine capacities

Used to:
	•	Generate a global cost–time outcome cloud
	•	Evaluate robustness of optimal strategies

⸻

Section 4: Post-Processing & Visualization
	•	Plots:
	•	Pareto frontiers by demand level
	•	AM-dominant vs TM-dominant regions
	•	Monte Carlo simulation outcomes
	•	Figures generated here correspond directly to thesis results

⸻

#### How to Use This Notebook
	•	Run cells sequentially for full reproducibility
	•	Individual sections can be executed independently once shared data is loaded
	•	Solver: Gurobi (license required)
	•	Monte Carlo sections may require longer runtime
