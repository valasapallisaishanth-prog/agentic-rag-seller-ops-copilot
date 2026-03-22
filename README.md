# Agentic RAG Copilot for Seller Operations

##  Overview

This project implements a **multi-agent Retrieval-Augmented Generation (RAG) system** designed to resolve seller support queries using structured reasoning and retrieval grounding.

Unlike traditional chatbot systems, this solution focuses on:
- **Domain-aware routing of queries**
- **Evidence-backed responses using retrieval**
- **Actionable resolution steps**
- **Multi-agent decision orchestration**

The system simulates how large-scale e-commerce platforms can build **intelligent support copilots** that go beyond answering queries and assist in operational decision-making.

---

##  Problem Statement

Seller support systems face complex, multi-domain issues such as:

- Listing suppression due to policy violations  
- Inventory mismatches and fulfillment delays  
- Account health warnings (late shipment, defect rate)  
- Payment and reimbursement disputes  

Traditional systems often:
- lack contextual understanding  
- produce generic or non-actionable responses  
- fail to explain root causes  

This project addresses these challenges using a **hybrid RAG + Agentic AI architecture**.

---

##  System Architecture

### End-to-End Pipeline

User Query  
→ Retrieval (Semantic Search)  
→ Router (Query Classification)  
→ Specialist Agent  
→ Manager Agent  
→ Final Response  

---

##  Multi-Agent Design

The system is composed of specialized agents, each responsible for a specific domain:

### 🔹 Policy Agent
Handles:
- Listing suppression  
- Compliance issues  
- Image/title violations  

---

### 🔹 Operations Agent
Handles:
- Inventory mismatch  
- Shipment delays  
- Fulfillment issues  

---

### 🔹 Account Health Agent
Handles:
- Performance warnings  
- Late shipment rate  
- Appeals and corrective actions  

---

### 🔹 Payments Agent
Handles:
- Reimbursement issues  
- Payment holds  
- Documentation validation  

---

### 🔹 Manager Agent (Orchestrator)

The Manager Agent:
- integrates retrieval and routing signals  
- consolidates agent outputs  
- produces final decision  

Output includes:
- Answer  
- Root Cause  
- Recommended Actions  
- Confidence Score  

---

##  Retrieval System (RAG)

- Uses **semantic search (sentence-transformers)**  
- Matches user queries with relevant knowledge base documents  
- Retrieves top-k context for grounding responses  

### Key Benefit:
Improves **response relevance** and reduces hallucination.

---

## Routing Strategy

The system uses a **hybrid routing mechanism**:

- Keyword-based classification (query intent)
- Retrieval-based scoring (context evidence)

These are combined to determine:
- the most relevant domain  
- the appropriate specialist agent  

---

##  Evaluation Approach

The system is evaluated across multiple dimensions:

### Retrieval
- Top-k relevance of retrieved documents  

### Routing
- Accuracy of domain classification  
- Keyword vs hybrid routing comparison  

### End-to-End System
- Response correctness  
- Action relevance  
- Grounding in retrieved evidence  

---

##  Example Output

### Input:
> My reimbursement request was rejected due to missing invoice  

### System Output:
- Category: Payments  
- Root Cause: Missing documentation  
- Actions:
  - Verify invoice completeness  
  - Attach required supporting documents  
  - Resubmit claim  

---

##  Interactive Demo

The project includes an interactive interface that allows:

- entering seller support queries  
- viewing selected agent and reasoning  
- inspecting retrieved evidence  
- understanding recommended actions  

---

##  Tech Stack

- Python  
- Pandas / NumPy  
- Sentence Transformers  
- Scikit-learn  
- Streamlit  

---

##  Sample Results

- Retrieval Top-1 Accuracy: ~0.80  
- Hybrid Routing Accuracy: ~0.85  
- Improved response grounding vs baseline LLM
- Retrieval Top-1 Accuracy: ~0.80  
- Hybrid Routing Accuracy: ~0.85  
- Improved response grounding vs baseline LLM  

The hybrid system demonstrated better domain classification and reduced irrelevant responses compared to single-agent or non-RAG approaches.

##  Key Insights

- Retrieval grounding significantly improves answer quality  
- Multi-agent systems enable domain specialization  
- Hybrid routing improves robustness across query types  
- Structured outputs enhance explainability and usability  

---

##  Future Improvements

- Integrate LLM-based reasoning (GPT / Gemini)  
- Add vector database (FAISS / Chroma)  
- Improve evaluation with groundedness metrics  
- Deploy as scalable service  

---

##  How to Run

```bash
pip install -r requirements.txt
streamlit run streamlit_app.py

##  Relevance to Large-Scale Systems

This project reflects real-world challenges in large-scale platforms where:

- queries span multiple operational domains  
- decision-making requires both retrieval and reasoning  
- explainability and actionability are critical  

This system reflects real-world decision systems used in large-scale e-commerce platforms, where support workflows require both retrieval grounding and multi-agent reasoning to generate actionable outcomes.

---

##  Author

**SaiShanth Valasapalli**

---

##  Summary

This project demonstrates how **multi-agent RAG systems can transform support workflows** by combining retrieval, routing, and agent orchestration into a unified decision system.

