# Zera Agent (Zero-prompt Evolving Refinement Agent)

## Overview

**Zera Agent** is a Zero-prompt Evolving Refinement Agent that automatically optimizes and iteratively improves prompts for various LLMs (Large Language Models).  
This agent systematically evaluates prompt quality, generates better prompts using meta-prompts, and is designed to enable repeated experiments on various datasets and models.

---

## Directory Structure & Roles

```
agent/
  app/           # Streamlit-based web UI and state management
  common/        # Common utilities such as API clients
  core/          # Core logic for prompt tuning and iterative result management
  dataset/       # Various benchmark datasets and data loaders
  prompts/       # System/user/meta prompt templates
  test/          # Unit test code
  __init__.py    # Package initialization

### agent directory
- **app/**: Streamlit-based web interface and state management
- **common/**: Common clients for communicating with various LLM APIs
- **core/**: Core logic for prompt auto-tuning and iterative result management
- **dataset/**: Loaders and folders for various benchmark datasets
- **prompts/**: System/user/meta/evaluation prompt templates
- **test/**: Test code for the prompt tuner

---

## Key Features

- **Prompt Auto-Tuning**:  
  - Iteratively improves system/user prompts to maximize LLM performance
  - Uses meta-prompts to guide the LLM to improve prompts directly

- **Support for Various Models and Datasets**:  
  - Supports various models such as OpenAI GPT, Anthropic Claude, Upstage Solar, local LLMs, etc.
  - Built-in benchmark datasets such as MMLU, GSM8K, CNN, MBPP, TruthfulQA, etc.

- **Automated Output Evaluation**:  
  - Automatically evaluates LLM outputs based on 8 criteria (accuracy, completeness, expression, reliability, conciseness, correctness, structural consistency, reasoning quality)
  - Improves prompts based on evaluation results

- **Various Evaluation Methods**:
  - **LLM-based Evaluation**: For each dataset, the LLM directly determines correctness, scores, and detailed evaluations
  - **BERTScore-based Evaluation**: Compares output similarity (F1, Precision, Recall, etc.) for each prompt using BERT embeddings
  - **LLM Judge-based Evaluation**: The LLM directly compares the outputs of two prompts and determines the winner/loser and reasons

- **Web UI Provided**:  
  - Intuitive experiment management and result visualization based on Streamlit

---

## Installation & Execution

1. Install dependencies
   ```
   pip install -r requirements.txt
   ```

2. Set environment variables  
   Enter API keys for OpenAI, Anthropic, etc. in the `.env` file

3. Run the web UI
   ```
   streamlit run agent/app/streamlit_app.py
   ```

---

## Example Use Cases

- Automatically generate optimal prompts for new tasks
- Automate LLM benchmark experiments and compare results
- Research and experiment with prompt engineering
- Quantitatively and qualitatively compare prompt performance using various evaluation methods (LLM, BERT, LLM Judge)

---

## Contribution & Contact

- Pull Requests and Issues are welcome
- Contact: [Project admin email or GitHub Issue]

---

This README is based on the actual code structure, main features, and the entire evaluation system.  
If you have any further questions or need detailed explanations, please let us know! 