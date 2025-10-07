Project Description

This project involves the optimization of a branched pipe system connecting four reservoirs (A, B, C, D) using Evolutionary Algorithms (EA). The optimization was performed using the EASY software, with a custom Fortran 90 code for hydraulic parameter calculations.

 Optimization Objectives
Single-Objective Optimization (SOO):

Maximize flow rate from reservoir A (Qa).

Equalize flow rates to reservoirs B, C, D (with tolerance ε = 10⁻⁴).

Multi-Objective Optimization (MOO):

Maximize Qa.

Minimize piping cost (proportional to surface area).

 Methods & Tools
Programming Language: Fortran 90 (code: branchP.f95)

Optimization Software: EASY

Hydraulic Calculation Method: Hardy-Cross

Design Variables:

Pipe diameters (Dki, Dlg, Dlm)

Junction coordinates (xk, yk, zk, xl, yl, zl, xm)

Constraints:

All flow rates > 0

Flow equality |Qc - Qb| ≈ |Qc - Qd| ≤ ε

Results

🔹 Single-Objective Optimization
Optimal Solution:

Qa = 0.094989 m³/s

Variables:
[0.06483, 0.06344, 0.13008, 127.05, -0.733, 29.72, 138.15, 3.78, 30.25, 61.44]

Method Comparison:

Best performance achieved with Binary Coding, 15 parents - 30 offspring, and PRNG = 1000.

🔹 Multi-Objective Optimization
Pareto Front showing trade-off between cost and flow rate.

Used Binary Gray Coding with increased function calls (3000).

🔹 Metamodel-Assisted EA (MAEA / IPE)
Used Radial Basis Function (RBF) as metamodel.

Reduced number of evaluations without significant quality degradation.

 Diagrams & Visualizations
The report includes:

Convergence diagrams for SOO & MOO

Pareto Fronts for multi-objective optimization

Comparison with/without metamodels (IPE)

 Conclusions
EAs are effective for nonlinear constrained optimization problems.

Multi-objective analysis provides valuable insights into trade-offs between objectives.

Metamodel usage can reduce computational cost while maintaining solution quality.

 How to Run
Compile the Fortran code:

bash
gfortran -o branchP.exe branchP.f95
Prepare input file task.dat

Run with EASY software using appropriate configuration files
