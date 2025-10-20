[![Forecastathon 2025](https://img.shields.io/badge/Forecastathon-2025-blue)](https://forecastathon.ai)
[![Python 3.10+](https://img.shields.io/badge/Built%20with-Python%203.10+-yellow)](https://www.python.org/)
[![MIT License](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)
[!Blockchain](https://img.shields.io/badge/Blockchain-Autonomy-blue)
[!Autonity](https://img.shields.io/badge/blockchain-Autonity-orange)

# Forecastathon-HLM3-Autonity

Hybrid project combining **Hierarchical Nonlinear Models (HLM3)** with **Blockchain Forecast Trading (Autonity + AFP)**.  
Developed for participation in the **Forecastathon.ai competition**, it bridges classical statistical modeling and decentralized finance forecasting.

---

# Under construction

> **Under Construction**: This repository is currently in development.
> The code and notebooks will be released once the initial version is ready.

---

## Project Structure

```

forecastathon-hlm3-autonity/
│
├── data/                <- Input and processed data
├── notebooks/           <- Jupyter notebooks for exploration & forecasting
│   ├── 01_data_preparation.ipynb
│   ├── 02_model_training.ipynb
│   └── 04_evaluation.ipynb
│
├── src/
│   ├── models/          <- HLM3 model in R
│   ├── scripts/         <- Forecast submission + pipeline logic
│   ├── utils/           <- Helper scripts (run_all.sh, logging, etc.)
│
├── logs/                <- Pipeline logs (auto-generated)
│
├── docs/
│   ├── OVERVIEW.md
│   └── results_summary.md
│
├── .env.example
├── .gitignore
├── requirements.txt
├── LICENSE
└── README.md

```

---

## Getting Started

### 1. Environment Setup

Clone this repository and install dependencies:

```
git clone https://github.com/<your_username>/forecastathon-hlm3-autonity.git
cd forecastathon-hlm3-autonity
pip install -r requirements.txt
```

### 2. Environment Variables

Rename `.env.example` to `.env` and fill in your information:

```
cp .env.example .env
```

Example:

```
AUTONITY_RPC_URL=https://rpc.autonity.io
PRIVATE_KEY=0xYOUR_PRIVATE_KEY_HERE
PRODUCT_ID=usdcz-forecast
NOTIFICATION_WEBHOOK=https://discord.com/api/webhooks/...
ENV=development
GAS_MULTIPLIER=1.0
```

### Warning!

 **Never commit your real `.env` file!**

---

## Running the Full Pipeline

Run the complete process (data prep → model → forecast submission):

```
 src/utils/run_all.sh
```

This will:

1. Log execution start time.
2. Run the **HLM3 R model** (`hlm3_model.R`).
3. Execute the **forecast submission** to the Forecastathon API.
4. Save all activity into `logs/pipeline.log`.
5. (Optional) Send a webhook notification once done.

---

## Model Description

The project integrates **Hierarchical Nonlinear Models (HLM3)** as forecasting engines.
Although implemented in R, the workflow automates execution and submission using **Python scripts** and **Autonity SDK** for blockchain interaction.

---

## Core Features

- Hybrid integration (R + Python + Blockchain)
- Automatic pipeline with error handling & logs
- Secure `.env` for key and endpoint management
- Optional Discord notification
- Ready for Forecastathon.ai competition deployment

---

## Forecast Submission

Forecasts are submitted automatically to Forecastathon’s API via:

```
python3 src/scripts/submit_forecast.py
```

Response logs are stored in `logs/pipeline.log`.

---

## References

* [Forecastathon.ai Documentation](https://forecastathon.ai/resources)
* [Autonity Blockchain Docs](https://docs.autonity.io)
* [AFP SDK Python (upcoming)](https://forecastathon.ai/resources)


---

### **docs/OVERVIEW.md**

```
# Project Overview

## Objective

This project is designed to test hybrid forecasting approaches that combine:
- Hierarchical Nonlinear Statistical Models (HLM3)
- Automated Python integration
- Blockchain-based forecast submission via Autonity (AFP)

## Pipeline Overview

**1. Data Preparation**  
Jupyter notebook `01_data_preparation.ipynb` loads and cleans weekly data.

**2. Model Training (R Layer)**  
`hlm3_model.R` fits the nonlinear hierarchical model.  
Results are stored as intermediate `.csv` outputs for integration.

**3. Forecast Submission (Python Layer)**  
`submit_forecast.py` reads model predictions and submits them to the Forecastathon API.

**4. Pipeline Execution (Automation)**  
`run_all.sh` orchestrates the full workflow with:
- Error handling  
- Log generation (`logs/pipeline.log`)  
- Optional webhook notification  

---

## Security Notes

- All sensitive variables (private key, RPC URL) are managed via `.env`.  
- The `.gitignore` excludes logs, raw data, and model outputs.  
- Never expose real keys in public commits.

---

## Blockchain Integration

Autonity SDK handles:
- Wallet connection (EVM-compatible)  
- Margin deposits  
- Forecast submissions  

Supports automatic reconnection and transaction safety checks.

---

## Future Work

- Implement custom market maker agent (AutEx integration)  
- Create DApp dashboard for real-time forecast tracking  
- Extend model to PyTorch equivalent for experimentation

---

## Credits

Project inspired by:
- USP Data Science Research (HLM3 models)
- Forecastathon.ai public challenge
- Autonity blockchain and AFP SDK team


---


## About the Author

I’m a Data Science and Analytics specialist (USP postgraduate) and Computer Engineer (UERJ) with a career spanning from **Pascal/C/Java roots** to **modern Machine Learning and AI**.

My academic and professional background includes:

* **Computation in general**
* **Machine Learning**
* **Statistical Machine Learning**
* **Deep Learning, LLMs, and Reinforcement Learning (ongoing specialization)**

---

## Contact  

- [LinkedIn](https://linkedin.com/in/celso-m-silva)  
- Or open an [issue](https://github.com/celsomsilva/forecastathon-hlm3-autonity) 

