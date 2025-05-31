# GenAI Project Planning Automation

A Python-based framework that uses Autogen and LangChain ( using models OpenAI GPT-4o-mini, Meta LLaMADeepSeek, Ollama) to automatically generate software project-management artifacts—charters, schedules, and task breakdowns—aligned with both Waterfall and Scrum methodologies. 
This repository contains five Jupyter notebooks demonstrating different model-pipeline combinations and their outputs.

---

## Project Overview

Effective software project planning requires well-structured charters, schedules, and task breakdowns. This project automates that process by integrating large language models (LLMs) into a Python-based pipeline. We use:

- **Autogen** (OpenAI GPT-4o-mini, Meta LLaMA)  
- **LangChain** (DeepSeek, Ollama)  

For each LLM, we create planning artifacts under **Waterfall** and **Scrum** methodologies. The goal is to compare consistency, completeness, and turnaround time across models and frameworks, producing output that follows industry best practices.

---

## Prerequisites & Installation

1. **Python Version**:  
   - Ensure you have Python 3.8+ installed.  

2. **Clone the Repository**:  
   ```bash
   git clone https://github.com/your-username/genai-project-planning.git
   cd genai-project-planning
   ```

3. **Create & Activate a Virtual Environment** (recommended):  
   ```bash
   python3 -m venv venv
   source venv/bin/activate       # macOS/Linux
   venv\Scripts\activate.bat      # Windows
   ```

   > **Note**: If you encounter version conflicts, consider using `pip install --upgrade --force-reinstall -r requirements.txt`.

---

## Configuration & API Keys

Certain notebooks require API keys or local model endpoints. Follow these steps:

1. **OpenAI API Key**  
   - Sign up for an OpenAI account (if you don’t have one).  
   - Create or retrieve your API key at [https://platform.openai.com/account/api-keys](https://platform.openai.com/account/api-keys).  
   - Export your key as an environment variable:
     ```bash
     export OPENAI_API_KEY="your_openai_api_key"
     ```
     On Windows PowerShell:
     ```powershell
     setx OPENAI_API_KEY "your_openai_api_key"
     ```

2. **Meta LLaMA Model Access**  
   - If you are using a hosted LLaMA endpoint (e.g., via a third-party provider), set the environment variable accordingly (e.g., `LLAMA_API_URL`).  
   - If you run LLaMA locally, ensure the `llama_index` (or equivalent) Python client is installed and configured.  

3. **DeepSeek & Ollama Configuration**  
   - DeepSeek: Obtain API credentials or endpoint from the DeepSeek dashboard.  
   - Ollama: Install and run the Ollama local server or use a remote endpoint.  
   - Export necessary environment variables (e.g., `DEEPISEEK_API_KEY` or `OLLAMA_API_URL`) so the notebooks can authenticate successfully.

---

## How to Run Notebooks

1. **Activate your virtual environment** (if not already active):  
   ```bash
   source venv/bin/activate       # macOS/Linux
   venv\Scripts\activate.bat      # Windows
   ```

2. **Launch Jupyter Notebook**:  
   ```bash
   jupyter notebook
   ```
   or
   ```bash
   jupyter lab
   ```

3. **Open and Run Each Notebook in Order**:  
   1. `01_OpenAI_Autogen.ipynb`  
   2. `02_MetaLLAMA_Autogen.ipynb`  
   3. `03_OpenAI_LangChain.ipynb`  
   4. `04_DeepSeek_LangChain.ipynb`  
   5. `05_Ollama_LangChain.ipynb`  

   - Each notebook is self-contained.  
   - Cells are organized into **Configuration**, **Prompt & Pipeline Definitions**, and **Run/Generate Output** sections.  
   - Ensure you run all cells top-to-bottom.  

4. **View Generated Outputs**  
   - After execution, each notebook writes planning artifacts to the `outputs/` directory.  
   - You can open the corresponding Markdown files (e.g., `outputs/waterfall/openai_autogen_waterfall_output.md`) to inspect the generated project charters, schedules, and task breakdowns.

---

## Notebook Summaries

Below is a brief description of each notebook’s purpose, inputs, and outputs. All notebooks share a common pipeline structure:

### Deepseek.ipynb
- **Description:** Implements an Autogen pipeline using DeepSeek to generate project charters, schedules, and task breakdowns for Waterfall and Scrum.

### Ollama.ipynb
- **Description:** Implements an Autogen pipeline using Ollama for creating project-management artifacts under both methodologies.

### OpenAI(gpt-4o-mini)_Autogen.ipynb
- **Description:** Defines an Autogen pipeline leveraging OpenAI GPT-4o-mini to produce planning artifacts, including charters, schedules, and task breakdowns.

### OpenAI_Autogen.ipynb
- **Description:** Implements a similar Autogen pipeline using the default OpenAI LLM for project planning.

### OpenAI_Langchain.ipynb
- **Description:** Uses LangChain with OpenAI GPT-4o-mini to create a chain of prompts and structured output parsing for project-management artifacts.

### Deeepseek_Langchain_LangGraph.ipynb
- **Description:** Utilizes LangChain and LangGraph with DeepSeek to generate detailed charters, schedules, and work breakdown structures.

### Llama_Langchain_LangGraph.ipynb
- **Description:** Implements a LangChain+LangGraph pipeline using Meta LLaMA to produce planning artifacts for Waterfall and Scrum.

### Ollama_Langchain.ipynb
- **Description:** Defines a LangChain pipeline with Ollama to generate charters, schedules, and task breakdowns.
---

Each Markdown file contains:

- **Project Charter**: Objectives, scope, stakeholders, deliverables  
- **High-Level Schedule**: Milestones, durations, dependencies  
- **Task Breakdown**: Detailed work breakdown structure with estimated effort  

Review these files to compare how each model and framework performed under Waterfall vs. Scrum.

---

## Key Technologies

- **Languages & Frameworks:**  
  - Python 3.8+  
  - Jupyter Notebook  
- **GenAI & LLM Frameworks:**  
  - Autogen (OpenAI GPT-4o-mini, Meta LLaMA)  
  - LangChain (OpenAI, DeepSeek, Ollama)  
- **Model Endpoints & APIs:**  
  - OpenAI API (GPT-4o-mini)  
  - Meta LLaMA endpoint (local or hosted)  
  - DeepSeek API (requires `DEEPISEEK_API_KEY`)  
  - Ollama (local server or remote API)  
- **Utilities & Libraries:**  
  - `pandas`, `json`, ’os` (standard Python packages)  
  - LangChain’s `LLMChain`, `SequentialChain`, and prompt-template utilities  
- **Version Control & DevOps:**  
  - Git/GitHub (repository management)  
  - (Optional) GitHub Actions or other CI to automate dependencies/format checks  

---
