# Hyperscaler Capital Expenditure and GPU/Memory Demand: An Exploratory Analysis

## Research Question

As hyperscalers (Microsoft, Amazon, Meta, Google, Oracle) ramp capital expenditure on AI infrastructure, does that spending show up in memory semiconductor demand — and if so, with what lag? This project traces the chain from hyperscaler capex, through Nvidia's data center revenue, to Micron's DRAM revenue and gross margin, to test whether the data supports the "AI-driven memory supercycle" narrative.

## Data Sources

- **Hyperscaler capex** — Operating cash flow, capital expenditure, and buybacks for Microsoft, Amazon, Meta, Google, and Oracle, Q1 2024–Q1 2026, sourced from quarterly earnings releases and 10-Qs. https://www.macrotrends.net/stocks/stock-screener

- **Nvidia revenue** — Quarterly revenue by segment (Data Centers and AI vs. Gaming/Devices/Automotive), 2014–2026, combining a long-run historical series with recent quarterly filings. https://ourworldindata.org/grapher/nvidia-quarterly-revenue-segment?time=earliest..2026-04-26

- **Micron financials** — DRAM revenue, NAND revenue, and gross margin, Q1 2025–Q1 2026 (calendar-aligned), sourced from Micron's 10-Q filings and earnings press releases. https://investors.micron.com/quarterly-results

- **DRAM market share** — Quarterly DRAM supplier market share (Samsung, SK Hynix, Micron, CXMT, Nanya), sourced from Counterpoint Research, used as supporting context. https://counterpointresearch.com/en/insights/global-dram-and-hbm-market-share

## Scope Note

SK Hynix and Samsung were considered as additional memory supplier case studies but excluded due to the added complexity of sourcing and translating Korean-language filings. Micron alone represents roughly 22–25% of the global DRAM market over this period, making it a reasonable single-company proxy for the broader memory market trend, though not a complete picture of it.

## Methodology Notes

- **Fiscal quarter alignment**: Nvidia and Micron both report on non-calendar fiscal years. Each company's fiscal quarter was mapped to the calendar quarter with the greatest date overlap, and relabeled accordingly for cross-dataset comparison. This mapping is an approximation — see notebook markdown cells for the exact mapping tables used.
- **Gross margin basis**: Micron's gross margin figures are GAAP for most quarters; one quarter (Q3 2025) uses a non-GAAP figure (~1 point higher than the GAAP equivalent) due to source availability. This is a minor, disclosed inconsistency.
- **Capex intensity**: Capex as a % of operating cash flow was calculated per hyperscaler per quarter to show how aggressively each company is funding its AI infrastructure buildout relative to its own cash generation (values over 100% indicate reliance on debt/cash reserves/equity rather than pure self-funding).

## Key Findings

1. **Hyperscaler capex has grown sharply across all five companies tracked**, with combined quarterly capex rising from roughly $81B (Q1 2025) to $146B (Q1 2026).
2. **Nvidia's Data Center segment now accounts for over 90% of total company revenue**, up from roughly 87% in early 2024 — gaming and other segments have become a minority of the business.
3. **Micron's DRAM revenue and gross margin have both risen sharply and move closely together** (r = 0.955, p = 0.003, n = 6), suggesting the current growth cycle is substantially price-driven — consistent with a supply-constrained, high-demand environment rather than volume growth alone.
4. **A lag correlation between hyperscaler capex and Micron's DRAM revenue is strongest at a 1-quarter lag** (r = 0.979, p = 0.021, n = 4) versus same-quarter (r = 0.879, p = 0.049, n = 5) or a 2-quarter lag (r = 0.916, p = 0.263, n = 3). This is directionally consistent with capex commitments translating into memory demand roughly one quarter later.
5. **DRAM revenue grew faster than capex over the same window** (DRAM revenue roughly 3x'd vs. capex roughly 1.8x'd), suggesting compounding effects from both higher volume and rising prices.

## Limitations

- **Small sample size.** The overlapping window across all three core datasets is only 4–6 quarters. Correlation and lag results should be read as directional/exploratory signals, not statistically robust conclusions — a longer time series (20+ quarters) would be needed for confident causal claims.
- **Correlation is not causation.** Both capex and memory revenue could be driven by a shared underlying factor (overall AI demand growth) rather than one directly causing the other.
- **Single memory supplier.** Findings are based on Micron only and may not generalize to the memory industry as a whole.
- **Capex-to-Nvidia allocation is not isolated.** This analysis does not attempt to estimate what share of hyperscaler capex specifically goes to Nvidia chips (versus buildings, networking, other hardware) — only the aggregate trends are compared.

## Tools

Python (pandas, matplotlib, seaborn, scipy) in a Jupyter Notebook (VS Code).

## Files

- `hyperscaler_capex_memory_analysis.ipynb` — main analysis notebook
- `Hyperscaler Financials Data - Cleaned Data.csv` — hyperscaler capex/OCF/buybacks dataset
- `nvidia_quarterly_revenue_cleaned.csv` — Nvidia segment revenue dataset
- `micron_financials_cleaned.csv` — Micron DRAM/NAND revenue and gross margin dataset
- `dram_market_share_counterpoint.csv` — DRAM market share by supplier
