# Large-Scale Machine Allocation Using Pyomo

## Overview

This project develops a Linear Programming model for production
planning and machine allocation using Python, Pyomo, and GLPK.

The company produces 12 industrial products using four limited
production resources:

- CNC
- Assembly
- Testing
- Packaging

The objective is to maximise total production profit while satisfying
machine capacity and market demand constraints.

## Problem

The model determines the optimal production quantity for each product.

## Objective

Maximise:

Total Profit = Sum of Product Profit × Production Quantity

## Constraints

The model includes:

1. CNC capacity
2. Assembly capacity
3. Testing capacity
4. Packaging capacity
5. Maximum market demand
6. Non-negative production quantities

## Methodology

The model was implemented using:

- Python
- Pyomo
- GLPK
- Pandas
- Matplotlib

## Decision Variables

x[p] = quantity of product p produced.

## Results

The model provides:

- Optimal production quantities
- Maximum total profit
- Machine hours used
- Unused machine capacity
- Machine utilisation
- Bottleneck identification

## Visualisation

The project includes visualisations of optimal production
and machine utilisation.

## Key OR Concepts

- Linear Programming
- Production Planning
- Product Mix
- Resource Allocation
- Capacity Constraints
- Bottleneck Analysis
- Optimisation
