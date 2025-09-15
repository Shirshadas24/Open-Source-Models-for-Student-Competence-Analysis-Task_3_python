# Python Screening Task 3: Evaluating Open Source Models for Student Competence Analysis
This repository contains my solution for Python Screening Task 3, which explores the use of open-source AI models for analyzing student-written Python code, generating meaningful prompts, and identifying conceptual gaps without giving away direct solutions.

## Project Overview
The project evaluates CodeBERT (for code embeddings) and CodeGen (for code continuation) to demonstrate how models can:
- Analyze student-written Python code
- Suggest prompts that assess understanding
- Highlight reasoning gaps (e.g., infinite loops, division by zero, unsafe input handling)
- Encourage deeper learning while avoiding spoon-feeding solutions

The solution is implemented in a Colab-ready Python notebook.

## Setup Instructions
Run on Google Colab
1. Open Google Colab
2. Upload the Task_3_demo.ipynb file
3. Run all cells to install dependencies and load models

Run Locally
```
git clone https://github.com/Shirshadas24/Open-Source-Models-for-Student-Competence-Analysis-Task_3_python.git
cd <Open-Source-Models-for-Student-Competence-Analysis-Task_3_python>
pip install -r requirements.txt
python main.py
```
Dependencies:
- torch
- transformers

## Research Plan
### Approach

I explored open-source LLMs trained on code (Hugging Face, Salesforce, Microsoft models) and evaluated their potential to assess student competence in Python. My method involved:
- Using CodeBERT for embeddings to capture semantic meaning of code.
- Using CodeGen to generate plausible continuations and prompts.
- Adding rule-based checks for conceptual gaps like infinite loops, division by zero, or unsafe inputs.

### Evaluation Criteria
- Suitability: Ability to analyze code beyond syntax (concept-level insights).
- Meaningfulness: Prompts must encourage reflection, not just provide answers.
- Accessibility: Freely available, open-source models that run in Colab.
- Trade-offs: Balancing accuracy (quality of insights), interpretability (human-readable prompts), and cost (free, open models).

## Reasoning
- Model Suitability: A suitable model must understand both syntax and semantics of Python, and generate feedback that nudges students toward deeper understanding.
- Testing Meaningful Prompts: I tested prompts by running student-written code through the pipeline and checking whether the feedback addressed conceptual errors rather than surface syntax.
- Trade-offs: While CodeGen sometimes generates multilingual outputs or partial solutions, it is lightweight and free. Larger models (e.g., CodeLlama, GPT-J) could offer higher accuracy but are more resource-heavy.
- Chosen Models:
   - CodeBERT: Strength → robust embeddings for code, good at capturing semantics. Limitation → not generative.
   - CodeGen (350M): Strength → small, fast, open-source code LLM. Limitation → may drift into irrelevant or multilingual continuations.

## References
[Microsoft CodeBERT]( https://huggingface.co/microsoft/codebert-base)
[Salesforce CodeGen](https://huggingface.co/Salesforce/codegen-350M-mono)
[Hugging Face Transformers](https://huggingface.co/docs/transformers/index)
