<div align="center">

# PM-Copilot

### A Multi-Agent LLM System for Financial Sentiment Analysis and Its Application in Equity & IPO Markets

<a href="https://drive.google.com/file/d/11MKsQK9IBriqFKv95wr4F_3HXMTXyFNy/view?resourcekey">
  <img src="assets/pm-copilot-demo-cover.png" alt="PM-Copilot demo video cover" width="780">
</a>

[![Demo Video](https://img.shields.io/badge/Watch-Demo%20Video-2f6fed?style=for-the-badge)](https://drive.google.com/file/d/11MKsQK9IBriqFKv95wr4F_3HXMTXyFNy/view?resourcekey)
[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg?style=for-the-badge)](LICENSE)

</div>

---

## Abstract

PM-Copilot is a portfolio-manager-oriented analytical co-pilot for monitoring financial markets, synthesizing multi-source sentiment, and supporting equity and IPO analysis. Instead of acting as an autonomous trading engine, the system organizes market, basket, and ticker-level evidence into a progressive dashboard so that human analysts can inspect signals, context, and limitations before making decisions.

This public repository currently hosts the project README, license, and demonstration material. The implementation code is still undergoing cleanup and will be uploaded later.

## Demo

Demo video: [PM-Copilot demo video](https://drive.google.com/file/d/11MKsQK9IBriqFKv95wr4F_3HXMTXyFNy/view?resourcekey).

## 📊 Performance Comparison Results

**Updated: May 1, 2026**

This section summarizes the two evaluation tracks most relevant to PM-Copilot's research claim. Unlike an autonomous trading benchmark, these results evaluate whether the system's sentiment layer produces calibrated, decision-support signals for listed equities and IPO analysis.

### Prompt Engineering: V0 vs V6 Sentiment Calibration

The production V6 prompt adds rubric anchors and sub-scores to reduce the over-clustering seen in the baseline V0 prompt. Raw V6 scores are noisier day to day, but after EMA-21 smoothing V6 slightly overtakes V0 in the share of ticker-lag combinations with significant Spearman correlation.

![Prompt engineering significance comparison](assets/prompt-engineering-significance.png)

*V6 overtakes the baseline after EMA-21 smoothing, supporting the final production choice of V6 prompt design plus EMA-21 smoothing.*

### IPO Sentiment Analysis: Pre-IPO Sentiment vs Day 1 Return

For the IPO use case, PM-Copilot uses an IPO-specific V6 prompt because pre-listing discussion differs from normal listed-equity sentiment. On the filtered seven-listing sample with at least two pre-IPO Reddit days, the final three-day pre-IPO sentiment score shows a strong positive relationship with Day 1 return.

![IPO sentiment correlation](assets/ipo-sentiment-correlation.png)

*Pre-IPO sentiment and Day 1 return show Spearman ρ = +0.93 with permutation p = 0.004 on the focused seven-listing evaluation set.*

## Overview

PM-Copilot addresses the information overload faced by portfolio managers who track many markets, thematic baskets, and individual securities. The system combines structured market data with unstructured news and social sentiment, then presents the result through three levels of analysis:

| Level | Purpose |
| --- | --- |
| **Market** | Summarize broad market movement and identify regions or themes that need attention. |
| **Basket** | Explain thematic portfolio performance with catalysts, movers, and AI-generated commentary. |
| **Ticker** | Produce deeper single-name analysis from multiple specialist agents and a synthesis layer. |

## System Design

The project follows a hierarchical multi-agent design. Specialist agents collect and interpret different evidence streams, while a synthesis agent reconciles their outputs into analyst-facing summaries.

| Component | Role |
| --- | --- |
| News Agent | Tracks recent company and market news. |
| Reddit / X Sentiment Agents | Extract social discussion volume, tone, and event context. |
| Technical Agent | Reviews price movement and market behavior. |
| Fundamental Agent | Adds company-level financial and business context. |
| Macro Agent | Captures broader market and economic background. |
| Synthesis Agent | Combines specialist evidence into a concise portfolio-manager view. |
| Dashboard | Provides market, basket, and ticker-level progressive disclosure. |

## Data Sources

The prototype uses a mix of market, news, and social data channels, including:

- daily equity price and return data
- thematic basket and ticker metadata
- Reddit discussion threads and comments
- X / Twitter-style social sentiment signals
- web news and search results
- company fundamentals, filings, and IPO-related reference data where available

The current demo focuses on decision-support outputs rather than fully reproducible public data release.

## Results & Demonstration

The demonstration highlights four main capabilities:

- a market overview for quickly locating stressed regions, sectors, or baskets
- basket-level commentary that explains daily movement and possible catalysts
- ticker-level multi-agent analysis for deeper single-name investigation
- sentiment evaluation studies for listed-equity and IPO-related use cases

PM-Copilot is designed as an analytical interface for human judgment. It does not execute trades, allocate capital, or claim causal prediction from sentiment alone.

## Repository Status

This repository is intentionally lightweight at this stage.

- Public demo video: available above
- README and license: available in this repository
- Source code: under final cleanup and planned for later upload
- Full reproducibility package: not yet released

## 📜 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgments

### Research Institution

- The Hong Kong University of Science and Technology (HKUST)
- [PEILab (Pervasive Intelligence Laboratory)](https://www.hkpeilab.com/)

### Faculty Advisors

- Prof. **Song GUO** - HKUST
- Prof. **Jie ZHANG** - HKUST

### Contributors

- Undergraduates: **Andy YUNG** (@Andy123qq4), **Lucas LI** (@lucashimselff), and **Teerth Jain** (@Hunter-175)
- Research Postgraduate: **Zeyu LIU** (MPhil)
