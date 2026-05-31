full code https://nbviewer.org/github/Abdulaziz-Jamaan/saudi-arabia-non-oil-gdp-vecm/blob/main/saudi-arabia-fdi-capex-vecm.ipynb

# Dynamics of Non-Oil Government Capital Expenditure and FDI in Driving Real Economic Growth in Saudi Arabia

An advanced macroeconometric project implementing a **Vector Error Correction Model (VECM)** to analyze the structural transmission channels of fiscal allocations and international private capital under Saudi Vision 2030.

---

## 1. Executive Summary & Research Goal
This empirical study examines the **long-run equilibrium relationship** and **short-run dynamic interactions** between non-oil government capital expenditure (`CapEx`), Foreign Direct Investment (`FDI_Inflow`), and real non-oil economic growth (`rGDP`) in Saudi Arabia. To control for domestic monetary conditions, interest rate environments, and credit constraints, the Saudi Interbank Offered Rate (`SAIBOR`) is introduced as a structural control variable.

Using a VECM framework, this project maps how public sector structural allocations interact with foreign private capital, identifying whether government intervention "crowds in" or "crowds out" foreign investment, and measuring the speed at which the non-oil economy returns to its long-term balanced growth path following unexpected macroeconomic shocks.

---

## 2. Theoretical Framework & Variable Rationale

The model is built around four specific time-series indicators gathered at a quarterly frequency ($N=36$ observations, spanning 2017 to present):

* **Real Non-Oil GDP (`rGDP`) [Target Variable]:** Serves as the primary proxy for sustainable economic diversification. By filtering out the volatile, OPEC+-dependent oil sector, we isolate the genuine structural growth driven by domestic modernization.
* **Government Capital Expenditure (`CapEx`) [Fiscal Policy Tool]:** Represents government spending allocated toward infrastructure, physical capital, and giga-projects. Econometrically, we track whether this acts as a foundation that lowers operating costs for international firms or temporarily displaces private sector resources.
* **Foreign Direct Investment (`FDI_Inflow`) [External Catalyst]:** Captures the inflow of international corporate capital, accounting for the transmission of global technological transfers, managerial expertise, and labor market upskilling.
* **Saudi Interbank Offered Rate (`SAIBOR`) [Monetary Control Variable]:** Controls for the domestic cost of capital and banking sector liquidity, ensuring estimated parameters for fiscal policy and foreign investment are isolated from monetary policy tightening or easing cycles.

---

## 3. Econometric Methodology Pipeline

Because macroeconomic time-series data typically exhibit non-stationary behaviors, running ordinary linear regressions can lead to spurious, invalid results. This study implements a rigorous time-series pipeline to ensure statistical integrity:

1. **Data Preprocessing & Logging:** Parsing quarterly sequences and validating logged structures.
2. **Unit Root Testing (Stationarity Check):** Applying Augmented Dickey-Fuller (ADF) tests to confirm all variables are integrated of order one, or $I(1)$.
3. **Johansen Cointegration Test:** Evaluating the system to identify the presence of a long-run binding relationship (Cointegrating Vectors).
4. **VECM Estimation:** Quantifying long-run structural coefficients ($\beta$) along with the short-run *Speed of Adjustment* ($\alpha$) parameter.
5. **Post-Estimation Diagnostics:** Testing for residual autocorrelation (Whiteness test) and multivariate normality.
6. **Dynamic Structural Analysis:** Projecting **Impulse Response Functions (IRF)** to trace the multi-quarter impact of structural policy shocks.

---

## 4. Key Empirical Findings

* **Long-Run Dynamics:** Government capital expenditure (`CapEx`) acts as a highly significant, powerful anchor for economic diversification, showing a long-run elasticity of **1.44** relative to non-oil GDP growth.
* **Short-Run Adjustments:** Foreign Direct Investment (`FDI_Inflow`) demonstrates incredible structural agility, acting as the primary error-correcting mechanism of the system by re-absorbing **89.7%** of quarterly systemic shocks within a single period.
* **Transitional Friction:** Impulse Response Functions reveal a short-run "crowding-out" effect from rapid public spending hikes, reflecting the temporary resource re-allocations required as massive infrastructure projects launch before they mature into long-run productive capacity.

---

## 5. Repository Structure
* `saudi-arabia-fdi-capex-vecm.ipynb` — The primary Jupyter Notebook containing the full Python code, mathematical steps, and generated output charts.
* `Data.xlsx` — Raw quarterly macroeconomic data sheet pulled from SAMA and GASTAT sources.
* `vecm_irf_rgdp.png` — Output visualization plot capturing the Impulse Response Function trajectories.

## 6. Dependencies & Installation
To run the notebook locally, ensure you have the following Python libraries installed:
```bash
pip install pandas numpy statsmodels matplotlib

