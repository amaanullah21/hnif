# Hafzan Network Impact Framework (HNIF) Portal

![Field](https://img.shields.io/badge/Field-Financial_Microstructure-blue.svg)
![Logic](https://img.shields.io/badge/Logic-Network_Theory-green.svg)
![Status](https://img.shields.io/badge/Status-Research_Ready-orange.svg)

An institutional-grade simulation platform for predicting trade-induced price impact across fragmented financial markets. This portal implements the framework proposed in the paper: **"A Network-Based Model for Predicting Market Impact in Fragmented Markets Using Venue-Level Dynamics"** by **Amaanullah Bhatti (Hafzan Osmanoğlu)**.

## 📖 Theoretical Context

In modern trading environments, liquidity is dispersed across multiple exchanges, dark pools, and ATS. Traditional models (like Kyle 1985) assume venue isolation. The **HNIF Framework** moves beyond this by treating trading venues as nodes in a correlation network, where price impact propagates based on the structural importance (centrality) of the venue and its connectivity to others.

### The Mathematical Model
The predicted impact on a target venue $j$ is calculated as:

$$Impact_{j} = \sum_{i=1}^{N} \left[ \left( \frac{TS_{i}}{D_{i} \cdot \sigma_{i}} \right)^{\beta} \cdot (C_{i} \cdot Corr_{ij}) \right]$$

- **$TS_{i}$**: Trade Size at venue $i$.
- **$D_{i}$**: Market Depth at venue $i$.
- **$\sigma_{i}$**: Asset Volatility at venue $i$.
- **$\beta$**: Non-linear impact exponent.
- **$C_{i}$**: Eigenvector centrality of the venue.
- **$Corr_{ij}$**: Correlation between source and target venues.

## 🚀 Key Features

-   **Propagation Simulator:** Model how a large trade on one venue "echoes" through the rest of the market network.
-   **Power-Law Modeling:** Configurable $\beta$ exponent to align with empirical market impact observations (e.g., square-root law).
-   **Impact Component Visualizer:** A dynamic bar chart (Chart.js) comparing local price pressure against network-propagated impact.
-   **Execution Benchmarking:** Professional classification of results to inform Smart Order Routing (SOR) strategies.

## 📊 Benchmark Classifications

| Score Range | Classification | Trading Implication |
| :--- | :--- | :--- |
| **< 10.0** | 🟢 Optimal | Minimal friction; safe for aggressive execution. |
| **10.0 – 35.0** | 🔵 Moderate | Standard propagation; split flow using SOR. |
| **35.0 – 60.0** | 🟠 High Pressure | Significant slippage and adverse selection risks. |
| **> 60.0** | 🔴 Critical | Systemic risk; potential for liquidity evaporation. |

## 🛠️ Tech Stack

-   **Frontend:** Custom CSS (Oxford Blue Professional Theme).
-   **Logic:** JavaScript (ES6) implementation of the HNIF power-law formula.
-   **Visualization:** Chart.js for real-time impact intensity mapping.

## 📝 Research Attribution & Citation

If you utilize the HNIF model in your quantitative research or trading infrastructure, please provide the following attribution:

**Author:** Amaanullah Bhatti (Hafzan Osmanoğlu)  
**Date:** April 15, 2025  
**ORCID:** [0009-0000-6922-0739](https://orcid.org/0009-0000-6922-0739)  
**Title:** *A Network-Based Model for Predicting Market Impact in Fragmented Markets Using Venue-Level Dynamics*

## 🔗 Connect with the Author

*   **Email:** [amaanullahbhatti@outlook.com](mailto:amaanullahbhatti@outlook.com)
*   **LinkedIn:** [linkedin.com/in/yourusername](https://linkedin.com/in/yourusername)
*   **GitHub:** [@yourusername](https://github.com/yourusername)

---
*Disclaimer: This portal is for research and simulation purposes. Real-world market impact estimation requires integration with live L2 order book data and historical volatility feeds.*
