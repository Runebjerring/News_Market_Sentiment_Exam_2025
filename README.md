# Algo-Trading with FinBERT: Crisis Alpha & Sentiment Analysis

## Project Objective
This project compares a state-of-the-art Natural Language Processing (NLP) model (FinBERT) against a traditional Lexical approach (Loughran-McDonald Dictionary) to test the hypothesis of "Crisis Alpha"---the ability of a sentiment strategy to act as a tail-risk hedge during major market crashes (2008 & 2020).

## Repository Structure
The repository is self-contained with the exception of the FinBERT model weights.

* algo_trading_project_hand_in.ipynb: The main analysis notebook.
* requirements.txt: List of necessary Python libraries.
* data/sp500_headlines.csv: The dataset used for analysis (Included).
* local_Loughran_McDonald_MasterDictionary_1993_2024/: The financial sentiment dictionary (Included).
* algo_trading_results_final.csv: The processed output data.

## Setup Instructions

### 1. Environment Setup
It is recommended to use a virtual environment to avoid version conflicts.

# Create and activate virtual environment
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate

# Install dependencies
pip install -r requirements.txt

### 2. Model Setup (Manual Action Required)
The FinBERT model weights are excluded from this repository due to file size limits. You must download them manually for the code to run.

1. Create the directory structure:
   mkdir -p models/finbert

2. Download the following 3 files from the Hugging Face "yiyanghkust/finbert-tone" repository:
   * pytorch_model.bin
   * config.json
   * vocab.txt

3. Place these files inside the models/finbert/ directory.

### 3. Execution
Open the notebook algo_trading_project_hand_in.ipynb and run all cells. The data and dictionary are already present in the repository, so no further downloads are required.

## Key Findings
1. Predictive Power: FinBERT demonstrated statistically significant predictive causality (p < 0.01), while the Dictionary model did not.
2. Crisis Alpha: The strategy achieved a -0.72 correlation with the market, successfully spiking during the 2008 and 2020 crashes.
3. Efficiency: The combined portfolio improved the Sharpe Ratio from 0.42 (Market) to 0.69 (Combined).