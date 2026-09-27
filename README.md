# Machine Allocation Optimization (Pyomo)

A linear programming model that determines the optimal production mix for a manufacturing company producing 12 industrial products across four shared production resources — CNC, Assembly, Testing, and Packaging — in order to maximize total profit subject to machine capacity and market demand limits.

## Problem

Decide how many units of each product to produce, x_p, to maximize profit without exceeding machine-hour capacities or exceeding market demand for any product.

**Decision variable**
x_p = number of units of product p produced

**Objective**
maximize Z = Σ_p Profit_p · x_p

**Constraints**
- Machine capacity, for each machine m: Σ_p Hours_{p,m} · x_p ≤ Capacity_m
- Demand: x_p ≤ Demand_p
- Non-negativity: x_p ≥ 0

Machine capacities (hours):

| Machine    | Capacity |
|------------|---------:|
| CNC        | 25,000   |
| Assembly   | 20,000   |
| Testing    | 12,000   |
| Packaging  |  8,000   |

## Project structure

.
├── machine_allocation.ipynb   # Main notebook: model, solve, results, plots
├── Data .xlsx                 # Input data (products, profit, hours/unit, demand) — not included, see below
├── requirements.txt
└── README.md

## Input data

The notebook reads a file named `Data .xlsx` in the same directory, with one row per product and the following columns:
- Product
- Profit (€ / Unit)
- CNC Hours / Unit
- Assembly Hours / Unit
- Testing Hours / Unit
- Packaging Hours / Unit
- Maximum Demand

Add your own `Data .xlsx` file to the repo root before running the notebook.

## Setup

pip install -r requirements.txt

The notebook uses the GLPK solver via Pyomo. Install it with:

# Debian/Ubuntu
sudo apt-get install glpk-utils

# macOS (Homebrew)
brew install glpk

# Conda
conda install -c conda-forge glpk

## Usage

Open and run `machine_allocation.ipynb` top to bottom. It will:
1. Load product data from `Data .xlsx`
2. Build the Pyomo model (sets, parameters, variables, objective, constraints)
3. Solve with GLPK
4. Report optimal production, max profit, machine hours used/unused/utilization, and the bottleneck machine
5. Generate bar charts of production quantities and machine utilization

## Tools

- Pyomo — optimization modeling
- GLPK — LP solver
- pandas — data handling
- matplotlib — visualization

## License

MIT (or your preferred license — update this section).
