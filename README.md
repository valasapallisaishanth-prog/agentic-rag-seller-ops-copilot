# Agentic RAG Copilot for Seller Operations

## Overview

This project implements a **multi-agent Retrieval-Augmented Generation (RAG) system** designed to resolve seller support issues using structured reasoning, retrieval grounding, and agent orchestration.

Unlike traditional LLM applications, this system goes beyond answering queries by:
- Identifying the **correct operational domain**
- Providing **root-cause explanations**
- Generating **actionable resolution steps**

The goal is to simulate a real-world **support copilot system** used in large-scale e-commerce platforms.

---

## Problem Statement

Seller support systems face challenges such as:
- Listing suppression due to policy violations  
- Inventory mismatches and fulfillment issues  
- Account health warnings (late shipment, defect rate)  
- Payment and reimbursement disputes  

Traditional chatbots:
- lack grounding in real documentation  
- produce generic or hallucinated responses  
- fail to provide actionable steps  

This project addresses these limitations using a **RAG + multi-agent architecture**.

---

## System Architecture

![Architecture](assets/architecture.png)

### Pipeline

1. **User Query**
2. **Retriever (Semantic Search)**
3. **Router (Query Classification)**
4. **Specialist Agent**
   - Policy Agent  
   - Operations Agent  
   - Account Health Agent  
   - Payments Agent  
5. **Manager Agent (Orchestrator)**
6. **Final Output**
   - Answer  
   - Root Cause  
   - Recommended Actions  
   - Confidence  

---

##  Agent Design

###  Policy Agent
Handles:
- Listing suppression  
- Compliance issues  
- Image/title violations  

---

###  Operations Agent
Handles:
- Inventory mismatch  
- Shipment delays  
- Fulfillment issues  

---

###  Account Health Agent
Handles:
- Performance warnings  
- Late shipment rate  
- Appeals  

---

###  Payments Agent
Handles:
- Reimbursement issues  
- Payment holds  
- Invoice/documentation problems  

---

###  Manager Agent
Combines:
- Retrieval evidence  
- Router decision  
- Agent output  

Produces:
- Final answer  
- Root cause  
- Action plan  
- Confidence score  

---

##  Retrieval System (RAG)

- Model: `sentence-transformers (MiniLM)`
- Technique: semantic similarity (cosine similarity)
- Input: user query
- Output: top-k relevant documents

---

##  Router Design

Hybrid routing approach:
- Keyword-based classification  
- Retrieval-based evidence scoring  
- Combined decision logic  

This improves:
- routing accuracy  
- robustness to ambiguous queries  

---

##  Evaluation

### Retrieval Evaluation
- Top-1 category accuracy

### Routing Evaluation
- Keyword vs Hybrid routing comparison

### System Evaluation
- End-to-end correctness (qualitative)
- Response grounding
- Action relevance

---

##  Example Output

### Input:
> "My reimbursement request was rejected due to missing invoice"

### Output:
- Category: Payments  
- Root Cause: Missing documentation  
- Actions:
  - Verify invoice completeness  
  - Attach required proof  
  - Resubmit claim  

---

##  Demo (Streamlit)

![UI](assets/demo_ui.png)
![Result](assets/demo_result.png)

The app allows:
- entering support queries  
- viewing agent selection  
- inspecting retrieved evidence  
- understanding reasoning  

---

##  Tech Stack

- Python  
- Pandas / NumPy  
- Sentence Transformers  
- Scikit-learn  
- Streamlit  

---

# Agentic RAG Copilot for Seller Operations

##  Overview

This project implements a **multi-agent Retrieval-Augmented Generation (RAG) system** designed to resolve seller support issues using structured reasoning, retrieval grounding, and agent orchestration.

Unlike traditional LLM applications, this system goes beyond answering queries by:
- Identifying the **correct operational domain**
- Providing **root-cause explanations**
- Generating **actionable resolution steps**

The goal is to simulate a real-world **support copilot system** used in large-scale e-commerce platforms.

---

##  Problem Statement

Seller support systems face challenges such as:
- Listing suppression due to policy violations  
- Inventory mismatches and fulfillment issues  
- Account health warnings (late shipment, defect rate)  
- Payment and reimbursement disputes  

Traditional chatbots:
- lack grounding in real documentation  
- produce generic or hallucinated responses  
- fail to provide actionable steps  

This project addresses these limitations using a **RAG + multi-agent architecture**.

---


### Pipeline

1. **User Query**
2. **Retriever (Semantic Search)**
3. **Router (Query Classification)**
4. **Specialist Agent**
   - Policy Agent  
   - Operations Agent  
   - Account Health Agent  
   - Payments Agent  
5. **Manager Agent (Orchestrator)**
6. **Final Output**
   - Answer  
   - Root Cause  
   - Recommended Actions  
   - Confidence  

---

##  Agent Design

###  Policy Agent
Handles:
- Listing suppression  
- Compliance issues  
- Image/title violations  

---

###  Operations Agent
Handles:
- Inventory mismatch  
- Shipment delays  
- Fulfillment issues  

---

###  Account Health Agent
Handles:
- Performance warnings  
- Late shipment rate  
- Appeals  

---

###  Payments Agent
Handles:
- Reimbursement issues  
- Payment holds  
- Invoice/documentation problems  

---

###  Manager Agent
Combines:
- Retrieval evidence  
- Router decision  
- Agent output  

Produces:
- Final answer  
- Root cause  
- Action plan  
- Confidence score  

---

##  Retrieval System (RAG)

- Model: `sentence-transformers (MiniLM)`
- Technique: semantic similarity (cosine similarity)
- Input: user query
- Output: top-k relevant documents

---

##  Router Design

Hybrid routing approach:
- Keyword-based classification  
- Retrieval-based evidence scoring  
- Combined decision logic  

This improves:
- routing accuracy  
- robustness to ambiguous queries  

---

##  Evaluation

### Retrieval Evaluation
- Top-1 category accuracy

### Routing Evaluation
- Keyword vs Hybrid routing comparison

### System Evaluation
- End-to-end correctness (qualitative)
- Response grounding
- Action relevance

---

##  Example Output

### Input:
> "My reimbursement request was rejected due to missing invoice"

### Output:
- Category: Payments  
- Root Cause: Missing documentation  
- Actions:
  - Verify invoice completeness  
  - Attach required proof  
  - Resubmit claim  

---

##  Demo (Streamlit)

![UI](assets/demo_ui.png)
![Result](assets/demo_result.png)

The app allows:
- entering support queries  
- viewing agent selection  
- inspecting retrieved evidence  
- understanding reasoning  

---

##  Tech Stack

- Python  
- Pandas / NumPy  
- Sentence Transformers  
- Scikit-learn  
- Streamlit  

---

**Key Insights**

Retrieval grounding reduces hallucination

Multi-agent systems improve task specialization

Routing improves response relevance

Combining ML + reasoning leads to better decisions

**Future Improvements**

Integrate LLM-based reasoning (GPT / Gemini)

Add vector database (FAISS / Chroma)

Improve evaluation with groundedness metrics

Deploy as scalable API service

**Relevance to Large-Scale Systems**

This architecture reflects real-world challenges in large-scale platforms where:

queries span multiple operational domains

decision-making requires both retrieval and reasoning

explainability and actions are critical

The system demonstrates how Agentic AI + RAG can support operational workflows.



**Summary**

This project demonstrates how multi-agent RAG systems can transform support workflows by combining retrieval, reasoning, and structured decision-making into a unified system.

