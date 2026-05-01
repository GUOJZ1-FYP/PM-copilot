<div align="center">

# PM-Copilot

### A Multi-Agent LLM System for Financial Sentiment Analysis and Portfolio Monitoring

**HKUST COMP 4981 Final Year Project · GUOJZ1 · 2025-2026**

[![Demo Video](https://img.shields.io/badge/Watch-Demo%20Video-2f6fed?style=for-the-badge)](https://drive.google.com/file/d/11MKsQK9IBriqFKv95wr4F_3HXMTXyFNy/view?resourcekey)
[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg?style=for-the-badge)](LICENSE)

</div>

---

## Abstract

PM-Copilot is a portfolio-manager-oriented analytical co-pilot for monitoring financial markets, synthesizing multi-source sentiment, and supporting equity and IPO analysis. Instead of acting as an autonomous trading engine, the system organizes market, basket, and ticker-level evidence into a progressive dashboard so that human analysts can inspect signals, context, and limitations before making decisions.

This public repository currently hosts the project README, license, and demonstration material. The implementation code is still undergoing cleanup and will be uploaded later.

## Demo

<a href="https://drive.google.com/file/d/11MKsQK9IBriqFKv95wr4F_3HXMTXyFNy/view?resourcekey">
  <img src="assets/pm-copilot-demo-cover.png" alt="PM-Copilot demo video cover" width="780">
</a>

GitHub READMEs do not render Google Drive video players directly, so the cover image above links to the public demo video: [PM-Copilot demo video](https://drive.google.com/file/d/11MKsQK9IBriqFKv95wr4F_3HXMTXyFNy/view?resourcekey).

## Overview

PM-Copilot addresses the information overload faced by portfolio managers who track many markets, thematic baskets, and individual securities. The system combines structured market data with unstructured news and social sentiment, then presents the result through three levels of analysis:

| Level | Purpose |
| --- | --- |
| Market | Summarize broad market movement and identify regions or themes that need attention. |
| Basket | Explain thematic portfolio performance with catalysts, movers, and AI-generated commentary. |
| Ticker | Produce deeper single-name analysis from multiple specialist agents and a synthesis layer. |

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

## Project Info

| Field | Value |
| --- | --- |
| Project ID | GUOJZ1 |
| Project Title | PM-Copilot: A Multi-Agent LLM System for Financial Sentiment Analysis and Its Application in Equity and IPO Markets |
| Authors | YUNG Ka Shing, LI Yuchen, JAIN Teerth |
| Advisors | Prof. Song GUO and Prof. Jie ZHANG |
| Institution | Department of Computer Science and Engineering, The Hong Kong University of Science and Technology |
| Course | COMP 4981 Final Year Project |
| Year | 2025-2026 |

## 📜 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgments

We sincerely thank Prof. Song GUO and Prof. Jie ZHANG for their supervision and guidance throughout this project. We also thank the HKUST Department of Computer Science and Engineering and PEILab for providing the academic environment and feedback that shaped PM-Copilot.

We are grateful to the open-source and research communities whose tools, datasets, and prior work made this project possible.
