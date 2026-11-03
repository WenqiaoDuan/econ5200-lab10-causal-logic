# econ5200-lab10-causal-logic
# Causal Logic and DAGs: Diagnosing Bad Controls

## Objective

I used causal diagrams (DAGs) and regression models to understand how different control variables affect causal estimates.

## Methodology

- I ran regressions with and without control variables.
- I tested collider bias, M-bias, and mediator effects.
- I compared experimental and observational estimates using the LaLonde dataset.
- I used `dag_utils.py` to find valid adjustment sets.
- I asked AI to suggest control variables and checked its answers using DAGs.
- I tested how an unobserved confounder could affect the estimate.

## Key Findings

- **Collider bias:** The estimate changed from -0.012 to -0.593, and R-squared increased to 0.585, although the true effect was zero.
- **M-bias:** Adding a pre-treatment control produced an estimate of -0.201 when the true effect was zero.
- **Mediator:** The estimated total effect was 3.978 (true 4.0), while the direct effect was 0.988 (true 1.0).
- **LaLonde study:** The experimental benchmark was $1,794. The CPS estimate was -$8,498 before adjustment and $699 after adjustment.
- **AI adjustment sets:** The AI estimated 4.047 both before and after my prompt revision, compared with the true effect of 4.0.
- **Sensitivity analysis:** An unobserved confounder explaining 33.8% of the residual outcome variation could double the estimate.

Overall, I learned that adding more control variables does not always improve causal estimates. Choosing the right variables based on the DAG is important.
