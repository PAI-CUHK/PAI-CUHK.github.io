---
title: "AIPatient: Simulating Patients with EHRs and LLM Powered Agentic Workflow"
date: 2024-09-27
tags: ["Simulated Patient", "Large Language Models", "Electronic Health Records", "Multi-agent Systems", "Retrieval Augmented Generation", "Medical QA", "Knowledge Graph"]
image:
  focal_point: 'top'
---

We present AIPatient, a novel framework that enhances medical education and research through an advanced simulated patient system built upon Electronic Health Records (EHRs) and powered by Large Language Models (LLMs).

**Paper**: [arXiv:2409.18924](https://arxiv.org/pdf/2409.18924)

---

## Overview

Simulated patient systems play a crucial role in modern medical education and research, providing safe, integrative learning environments and enabling clinical decision-making simulations. Large Language Models (LLM) could advance simulated patient systems by replicating medical conditions and patient-doctor interactions with high fidelity and low cost. However, ensuring the effectiveness and trustworthiness of these systems remains a challenge, as they require a large, diverse, and precise patient knowledgebase, along with a robust and stable knowledge diffusion to users. 

Here, we developed AIPatient, an advanced simulated patient system with AIPatient Knowledge Graph (AIPatient KG) as the input and the Reasoning Retrieval-Augmented Generation (Reasoning RAG) agentic workflow as the generation backbone. AIPatient KG samples data from Electronic Health Records (EHRs) in the Medical Information Mart for Intensive Care (MIMIC)-III database, producing a clinically diverse and relevant cohort of 1,495 patients with high knowledgebase validity (F1 0.89). Reasoning RAG leverages six LLM powered agents spanning tasks including retrieval, KG query generation, abstraction, checker, rewrite, and summarization. This agentic framework reaches an overall accuracy of 94.15% in EHR-based medical Question Answering (QA), outperforming benchmarks that use either no agent or only partial agent integration. Our system also presents high readability (median Flesch Reading Ease 77.23; median Flesch Kincaid Grade 5.6), robustness (ANOVA F-value 0.6126, p>0.1), and stability (ANOVA F-value 0.782, p>0.1). The promising performance of the AIPatient system highlights its potential to support a wide range of applications, including medical education, model evaluation, and system integration.

## Core Methodology

The methodology of the AIPatient system is primarily structured around two key components:

### 1. AIPatient Knowledge Graph (AIPatient KG)

This graph serves as the foundational knowledge base, containing patient data extracted from the Medical Information Mart for Intensive Care (MIMIC-III) database. Key features include:

- **Diverse Patient Cohort**: 1,495 patient profiles offering clinically diverse scenarios
- **High Accuracy**: F1 score of 0.89, indicating substantial accuracy in capturing medical data through Named Entity Recognition (NER)
- **Structured Organization**: Medical entities such as symptoms, medical histories, allergies, and vital signs organized into nodes, interlinked by edges depicting relationships (e.g., HAS_SYMPTOM, HAS_MEDICAL_HISTORY)
- **LLM-based NER**: Utilizes advanced NER techniques to transform unstructured clinical notes (discharge summaries) into structured data
- **Graph Database**: Efficiently stored and queried using Neo4j for complex relationship analysis

### 2. Reasoning Retrieval-Augmented Generation (Reasoning RAG) Workflow

This multi-agent system provides a dynamic method for processing natural language queries and generating context-appropriate responses. The workflow consists of three primary stages:

#### Retrieval Stage
- **Retrieval Agent**: Selects relevant nodes and relationships from the AIPatient KG based on user queries
- **KG Query Generation Agent**: Formulates Cypher queries to extract pertinent information from the graph database

#### Reasoning Stage
- **Abstraction Agent**: Simplifies and rephrases user queries into more general forms for better processing
- **Checker Agent**: Verifies alignment between retrieved information and user inquiries, with up to three re-evaluation attempts for quality assurance

#### Generation Stage
- **Rewrite Agent**: Transforms KG query results into natural language while considering simulated patient personality traits
- **Summarization Agent**: Updates and maintains conversation context to enhance continuity for multi-turn interactions

## Technical Specifications

### Named Entity Recognition (NER)
- LLM-based NER system for extracting medical entities from unstructured discharge summary data
- Establishes relationships like "HAS_FAMILY_MEMBER" and "HAS_MEDICAL_HISTORY" within the graph structure

### Graph Database Utilization
- Hosted in Neo4j for complex multi-faceted relationship queries
- Enables nuanced medical inquiries that traditional document-based retrieval systems may fail to capture

### Cypher Query Language
- Optimally navigates graph data complexities compared to linear document retrieval methods
- Provides insightful connections among diverse medical entities

### Performance Evaluation
- **Ablation Studies**: Configurations using both Retrieval Agent and Abstraction Agent significantly outperformed simpler setups
- **Overall QA Accuracy**: 94.15% in EHR-based medical Question Answering
- **Readability Metrics**: 
  - Median Flesch Reading Ease: 77.23
  - Median Flesch-Kincaid Grade Level: 5.6
- **Robustness**: ANOVA F-value 0.6126 (p>0.1)
- **Stability**: ANOVA F-value 0.782 (p>0.1)

## Key Contributions

1. **Advanced Knowledge Graph**: AIPatient KG provides a robust foundation with high validity (F1 0.89) derived from real EHR data
2. **Multi-Agent Architecture**: Six specialized LLM agents working in concert for comprehensive patient simulation
3. **Superior Performance**: 94.15% accuracy outperforming existing benchmarks
4. **High Readability**: Ensures accessible communication for educational purposes
5. **Robustness and Stability**: Consistent performance across varied scenarios and question formulations

## Applications and Impact

The AIPatient framework offers transformative potential for:

- **Medical Education**: Enhanced training environments for healthcare professionals
- **Clinical Decision-Making**: Safe simulation of patient interactions and scenarios
- **Research**: Model evaluation and system integration testing
- **Curriculum Development**: Integration within medical education programs

## Future Directions

Future enhancements could include:

- **Broader Data Scope**: Incorporating wider variety of healthcare scenarios
- **Multimodal Integration**: Adding medical imaging and other data modalities
- **Real-time Clinical Environments**: Adapting for live clinical settings
- **Enhanced Training Landscapes**: Further enriching educational outcomes for healthcare professionals

## Conclusion

The AIPatient framework exemplifies a transformative approach to patient simulation through EHR data and LLM-powered interactions, emphasizing structured retrieval and knowledge dissemination in a manner conducive to enhancing medical training and decision-making processes. By embedding these systems within medical curricula and research protocols, we propose significant advancements in how interactions with simulated patients can impact educational outcomes and clinical preparedness.