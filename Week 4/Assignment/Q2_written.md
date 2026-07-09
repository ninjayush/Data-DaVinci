# Q2 Written Questions

## Question 2.2
**Argument against MAPE for fleet management/HR:**
MAPE (Mean Absolute Percentage Error) treats over-prediction and under-prediction with symmetric penalties in terms of percentages. However, for fleet management and human resources, the costs are heavily asymmetric:
- **Under-predicting demand**: Leads to a shortage of fleets and staff, resulting in canceled flights, severe customer dissatisfaction, and massive revenue loss (constrained by peak demand).
- **Over-predicting demand**: Leads to idle staff or empty seats, which incurs a known operational cost, but is often less damaging than turning away paying customers.

**Suggested Metric:**
An asymmetric loss function or a weighted metric. A commonly used metric for inventory/fleet planning is the **Pinball Loss (Quantile Loss)**, where you forecast a specific quantile (e.g., the 90th percentile of demand) to ensure sufficient capacity. Alternatively, a custom cost-weighted MAPE or **wMAPE** (Weighted MAPE) can be used, heavily penalizing under-predictions.

## Question 2.3
**Statistical Test for Pre-COVID vs. Post-COVID mean difference:**
Since $\Delta Y$ is modeled as $\Delta Y = \mu + \mathcal{N}(0, \sigma)$ (which means the differences are normally distributed), we are testing if the unknown constant mean $\mu$ (the drift) has changed between the two periods (pre-Dec 2019 vs. post-Jan 2022).
Since $\sigma$ is known, we could perform a **Two-Sample Z-test**.
If $\sigma$ is assumed to be different for both periods or unknown in practice, we would perform a **Welch's Two-Sample t-test**.
