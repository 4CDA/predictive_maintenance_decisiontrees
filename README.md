# Using Gen AI to Support Maintenance Engineering Workflows

## Overview

This project demonstrates how **Generative AI (Gen AI)** and **Large Language Models (LLMs)** can enhance industrial maintenance workflows by:

- Automating inspection report summaries  
- Generating technician-style recommendations  
- Categorizing maintenance actions for workflow routing  
- Improving decision-making and reducing downtime  

---

## What is Gen AI?

Generative AI models produce new content (text, code, images) by learning from large datasets. LLMs, like OpenAI's GPT series, interpret and generate human-like text, enabling automation of complex language tasks without retraining.

---

## Features

- Ingest and process sensor data from industrial engines  
- Convert sensor readings into structured prompts for LLM  
- Use OpenAI GPT-4o-mini to generate inspection summaries and maintenance actions  
- Automatically categorize actions (`Monitor`, `Flag for Inspection`, `No Action`)  
- Evaluate model accuracy against rule-based baseline  
- Export results for integration with enterprise systems (e.g., SAP)  

---

## How It Works

1. **Load Data**  
   The repository includes 500 engine inspection records with sensor metrics and failure types (`Data/maintenance.csv`).  

2. **Create Prompts**  
   Translate sensor values into technician-style prompts requesting JSON outputs.  

3. **Query LLM**  
   Send prompts to GPT-4o-mini and receive structured responses.  

4. **Process Results**  
   Store comments and recommended actions; apply error handling.  

5. **Categorize Actions**  
   Classify actions for workflow routing based on keywords.  

6. **Evaluate**  
   Compare AI recommendations to baseline logic and measure accuracy (99.8%).  

---

## Example Output

```json
{
  "comment": "Engine ID 263 shows signs of power failure with elevated vibration levels at 42.0. Operational hours are at 81.3, indicating potential wear. Immediate attention required.",
  "action": "Conduct thorough inspection and address vibration; consider part replacement."
}
```

## Installation & Usage

1. Clone the repository

2. Install dependencies:

```bash
pip install -r requirements
```

3. Set your OpenAI API key in environment variables

4. Run the main script or notebook to generate reports

5. Review output in Data/generate_maintenance_report.csv

## Performance
Accuracy: 99.8% compared to rule-based baseline

Recall: 100% on monitoring low-risk cases

Precision: Perfect for flagging inspections

## Cost & Scalability
Processing 500 records costs about $0.03 USD on GPT-4o-mini, demonstrating affordability at scale.

Repository Structure
``` bash
Copy
Edit
/
├── Data/                       # Included sensor data and generated outputs CSV
├── scripts/                    # Python modules for each workflow step
├── README.md                   # Project overview and instructions
├── requirements.txt            # Dependencies list
└── main.py / notebook.ipynb    # Orchestration scripts```
