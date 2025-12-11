# PriMAS-LLM: a Privacy-Preserving Multi-Agent System for Large Language Models!

It is a framework designed to evaluate and mitigate **privacy leakage** in **LLM-based multi-agent systems**. It provides a controlled environment where multiple agents exchange natural language messages while a privacy filter enforces selective masking of sensitive information.

The system supports experiments using **real datasets**, including:

- **Amazon Polarity Dataset** — consumer reviews containing realistic natural language patterns  
- **MIMIC-III Clinical Demo Dataset (`PATIENTS.csv`)** — synthetic patient-identifying and demographic information  

This framework is suitable for research in:

- Privacy-preserving AI  
- Multi-agent LLM safety  
- Sensitive data handling  
- Healthcare NLP  
- AI system auditing  
- Responsible AI and regulatory compliance  

---

## Key Features

- **Multi-Agent LLM Architecture**
  - `IntakeAgent`: Full visibility of sensitive content  
  - `PlannerAgent`: Internal analyst with full access  
  - `ExplainerAgent`: Restricted-access agent for sensitive information  

- **Privacy Enforcement**
  - Redacts:
    - Emails  
    - Phone numbers  
    - Dates (`YYYY-MM-DD`)  
    - MIMIC patient identifiers (SUBJECT_ID, DOB, DOD, EXPIRE_FLAG)
    - High-risk keywords (refund, credit card, etc.)
  - Ensures agents only view data they are authorized to access  

- **Real Dataset Integration**
  - Processes Amazon reviews as input messages  
  - Processes MIMIC-III patient summaries from `PATIENTS.csv`  
  - Automatically injects synthetic emails & phone numbers for testing  

- **Leakage Quantification**
  - Counts sensitive tokens before/after filtering  
  - Logs raw vs masked messages  
  - Produces data tables for analysis  

- **Visualization Tools**
  - Bar charts for leakage comparison between agent types  
  - Easy export into research papers or presentations  

- **LLM-Ready**
  - Uses dummy local LLM by default (no API cost)  
  - Switch to OpenAI models by setting `USE_REAL_LLM=True`  

---

##  Installation

Run in Google Colab or local Python:

```bash
pip install datasets pandas matplotlib
```
---

To enable OpenAI LLMs:

```bash
pip install openai
export OPENAI_API_KEY="your_api_key_here"
```



