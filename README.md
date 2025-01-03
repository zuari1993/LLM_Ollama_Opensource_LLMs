Compares several open source LLM model with 50 prompts. All these LLM models are Low-parameter & Low latency, Edge device capable. 
The output excel file summarizes the results along with the time it takes. 

# Comparing Low-Parameter, Low-Latency LLMs for Edge Devices

This repository provides a Jupyter Notebook for evaluating several lightweight large language models (LLMs) on a set of 50 prompts. The goal is to compare performance in terms of response quality and execution time. The evaluated models are low-parameter and low-latency, designed to be deployable on edge devices.

## Features

- **Model Comparisons**: Tests multiple open-source LLMs, such as:
  - `llava-phi3`
  - `moondream`
  - `llama3.2:1b`
  - `llama3.2`
  - `granite3.1-moe:3b`
  - `smollm2:1.7b-instruct-fp16`
- **Prompt Dataset**: Uses a curated dataset of 50 human-like prompts covering diverse topics like Excel automation, array formulas, and niche questions.
- **Output Summary**: Generates an output CSV file summarizing:
  - Model responses to each prompt.
  - Time taken by each model to generate a response.

## Models Overview

| Model                        | Parameters (Millions) | Latency (Edge Device Capable) | Notes                           |
|------------------------------|-----------------------|-------------------------------|---------------------------------|
| `llava-phi3`                 | 3.8 Billion           | Yes                           | Balanced for general use       |
| `moondream`                  | 1.6 Billion           | Yes                           | Efficient with good accuracy   |
| `llama3.2:1b`                | 1 Billion             | Yes                           | Compact version of LLaMA 3.2   |
| `llama3.2`                   | 3.2 Billiob           | Yes                           | General-purpose NLI tasks      |
| `granite3.1-moe:3b`          | 3 Billion             | Yes                           | Optimized for few-shot tasks, **very low latency **  |
| `smollm2:1.7b-instruct-fp16` | 1.7 Billion           | Yes                           | Instruction-tuned, compact     |

## Model Output Summary

| Index | Topic                 | Prompt                                  | Model Output (`llava-phi3`) | Execution Time (`llava-phi3`) | Model Output (`moondream`) | Execution Time (`moondream`) | ... |
|-------|-----------------------|-----------------------------------------|-----------------------------|-------------------------------|----------------------------|------------------------------|-----|
| 0     | Array Formulas        | Sum product but not regular.            | [Response]                  | [Time Taken]                  | [Response]                 | [Time Taken]                | ... |
| 1     | Automation and Macros | Can I assign a macro to a button?       | [Response]                  | [Time Taken]                  | [Response]                 | [Time Taken]                | ... |
| ...   | ...                   | ...                                     | ...                         | ...                           | ...                        | ...                          | ... |


## Installation

### Dependencies
Install the required Python libraries by running:

```bash
pip install langchain_community langchain_experimental langchain_ollama unstructured pdf2image pdfminer open-clip-torch pylzma langchain faiss-cpu PyPDF2 transformers -U
