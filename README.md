# Auto Repair AI Assistant

Auto Repair AI Assistant is an AI-powered diagnostic and repair planning service designed for professional automotive technicians and internal repair teams.

The system helps mechanics transform unstructured fault descriptions into structured diagnostic information, retrieve relevant repair cases and service manuals, and generate practical, step-by-step repair plans with supporting references.

Instead of relying only on general-purpose language model knowledge, the service combines structured vehicle information, diagnostic trouble codes, real-world repair cases, and technical manuals through a Retrieval-Augmented Generation architecture. This allows the system to provide more accurate, traceable, and context-aware repair recommendations.

## Key Features

* **Natural Language Fault Understanding**
  Extracts vehicle brand, model, year, engine type, mileage, symptoms, diagnostic trouble codes, and previous repair attempts from free-text input.

* **Structured Diagnostic Output**
  Converts mechanic notes into standardized diagnostic records for easier searching, analysis, and reuse.

* **RAG-Based Repair Knowledge Retrieval**
  Retrieves relevant repair cases, service manual sections, diagnostic procedures, fault code explanations, and component knowledge.

* **AI-Generated Repair Plans**
  Generates practical repair suggestions, likely root causes, inspection steps, recommended actions, and safety warnings.

* **Traceable References**
  Provides citations from repair manuals, historical cases, and internal knowledge bases to support every recommendation.

* **Enterprise-Ready Architecture**
  Designed for private deployment, internal knowledge management, role-based access, logging, feedback collection, and future model fine-tuning.

## Target Users

This project is built for:

* Automotive repair technicians
* Repair shop groups
* Vehicle maintenance companies
* Fleet maintenance teams
* Automotive after-sales service departments
* Internal technical support teams

## Typical Use Case

A mechanic enters a fault description such as:

> “2020 Volkswagen Passat 2.0T, 80,000 km, engine shakes during cold start, OBD reports P0302, spark plugs have already been replaced.”

The system analyzes the input, identifies the vehicle and symptoms, retrieves similar cases and service manual procedures, and generates a diagnostic plan such as:

1. Check freeze frame data.
2. Swap the cylinder 2 ignition coil with another cylinder.
3. Clear the fault code and perform a road test.
4. If the misfire code moves to another cylinder, replace the ignition coil.
5. If the fault remains on cylinder 2, inspect the injector, compression, and intake leakage.

## Technical Architecture

The service is designed around a Python-based backend and a modular AI workflow:

* **FastAPI** for API service
* **Pydantic** for structured input and output validation
* **Qdrant / Milvus / pgvector** for vector search
* **Elasticsearch / OpenSearch** for keyword and fault-code retrieval
* **LlamaIndex / LangChain** for RAG pipeline construction
* **vLLM / Ollama / OpenAI-compatible APIs** for LLM inference
* **PostgreSQL** for repair cases, user feedback, and diagnostic records
* **LangGraph or custom workflow engine** for multi-step diagnostic reasoning

## Project Goal

The goal of Auto Repair AI Assistant is to build a reliable AI copilot for automotive repair professionals.

It does not aim to replace experienced mechanics. Instead, it helps technicians search knowledge faster, reduce missed diagnostic steps, standardize repair reasoning, and make better decisions based on historical cases and verified technical documents.

## Roadmap

* Build an MVP for text-based fault diagnosis
* Import repair cases, fault code databases, and service manuals
* Implement hybrid retrieval using fault codes, vehicle metadata, and semantic search
* Generate structured repair plans with references
* Add technician feedback collection
* Support private LLM deployment
* Fine-tune domain-specific models using verified repair data
* Integrate OBD-II data input and diagnostic device connections
