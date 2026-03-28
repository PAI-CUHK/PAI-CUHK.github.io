---
title: "🧑🏽‍⚕️ [PUBLISHED] AIPatient: Simulating Patients with EHRs and LLM Powered Agentic Workflow"
date: 2024-09-27
tags: ["Simulated Patient", "Large Language Models", "Electronic Health Records", "Multi-agent Systems", "Retrieval Augmented Generation", "Medical QA", "Knowledge Graph"]
share: false
image:
  focal_point: 'top'
---


🎉 We present AIPatient, a novel framework that enhances medical education and research through an advanced simulated patient system built upon Electronic Health Records (EHRs) and powered by Large Language Models (LLMs).



<div class="d-flex flex-wrap" style="gap: 16px; margin: 1.5em 0;">
  <a href="https://huiziy.github.io/aipatient-overview/" target="_blank" style="display: inline-flex; align-items: center; background-color: #1a73e8; color: white; padding: 10px 24px; border-radius: 24px; text-decoration: none; font-weight: 500; font-family: Roboto, Arial, sans-serif; box-shadow: 0 1px 3px rgba(0,0,0,0.12), 0 1px 2px rgba(0,0,0,0.24); transition: background-color 0.3s;" onmouseover="this.style.backgroundColor='#1557b0'" onmouseout="this.style.backgroundColor='#1a73e8'">
    <i class="fas fa-globe" style="margin-right: 8px;"></i> Project Page
  </a>
  <a href="https://www.nature.com/articles/s43856-025-01283-x" target="_blank" style="display: inline-flex; align-items: center; background-color: white; color: #1a73e8; border: 1px solid #dadce0; padding: 10px 24px; border-radius: 24px; text-decoration: none; font-weight: 500; font-family: Roboto, Arial, sans-serif; transition: background-color 0.3s;" onmouseover="this.style.backgroundColor='#f8f9fa'" onmouseout="this.style.backgroundColor='white'">
    <i class="fas fa-file-alt" style="margin-right: 8px;"></i> Read Published Paper
  </a>
</div>

---

<h2 style="color: #1a73e8; border-bottom: 2px solid #e8eaed; padding-bottom: 10px; margin-top: 2em; margin-bottom: 1em; font-weight: 500;">🔍 Overview</h2>

<div style="background-color: #f8f9fa; border-left: 4px solid #1a73e8; padding: 20px; border-radius: 4px; color: #3c4043; font-size: 1.05em; line-height: 1.6; margin-bottom: 2em;">
Simulated patient systems play a crucial role in modern medical education and research, providing safe, integrative learning environments and enabling clinical decision-making simulations. Large Language Models (LLM) could advance simulated patient systems by replicating medical conditions and patient-doctor interactions with high fidelity and low cost. However, ensuring the effectiveness and trustworthiness of these systems remains a challenge, as they require a large, diverse, and precise patient knowledgebase, along with a robust and stable knowledge diffusion to users. 

Here, we developed AIPatient, an advanced simulated patient system with AIPatient Knowledge Graph (AIPatient KG) as the input and the Reasoning Retrieval-Augmented Generation (Reasoning RAG) agentic workflow as the generation backbone. AIPatient KG samples data from Electronic Health Records (EHRs) in the Medical Information Mart for Intensive Care (MIMIC)-III database, producing a clinically diverse and relevant cohort of 1,495 patients with high knowledgebase validity (F1 0.89). Reasoning RAG leverages six LLM powered agents spanning tasks including retrieval, KG query generation, abstraction, checker, rewrite, and summarization. This agentic framework reaches an overall accuracy of 94.15% in EHR-based medical Question Answering (QA), outperforming benchmarks that use either no agent or only partial agent integration. Our system also presents high readability (median Flesch Reading Ease 77.23; median Flesch Kincaid Grade 5.6), robustness (ANOVA F-value 0.6126, p>0.1), and stability (ANOVA F-value 0.782, p>0.1). The promising performance of the AIPatient system highlights its potential to support a wide range of applications, including medical education, model evaluation, and system integration.
</div>

<h2 style="color: #1a73e8; border-bottom: 2px solid #e8eaed; padding-bottom: 10px; margin-top: 2em; margin-bottom: 1em; font-weight: 500;">⚙️ Core Methodology</h2>

The methodology of the AIPatient system is primarily structured around two key components:

<h3 style="color: #202124; margin-top: 1.5em; margin-bottom: 0.8em; font-weight: 500;">1. AIPatient Knowledge Graph (AIPatient KG)</h3>

<p style="color: #3c4043;">This graph serves as the foundational knowledge base, containing patient data extracted from the Medical Information Mart for Intensive Care (MIMIC-III) database. Key features include:</p>

<div style="background-color: white; border-left: 4px solid #9c27b0; padding: 16px; border-radius: 4px; box-shadow: 0 1px 2px rgba(0,0,0,0.1); margin-bottom: 2em; margin-top: 1em;">
  <ul style="margin: 0; padding-left: 20px; color: #5f6368; font-size: 0.95em;">
    <li style="margin-bottom: 8px;"><b>Diverse Patient Cohort:</b> 1,495 patient profiles offering clinically diverse scenarios.</li>
    <li style="margin-bottom: 8px;"><b>High Accuracy:</b> F1 score of 0.89, indicating substantial accuracy in capturing medical data through Named Entity Recognition (NER).</li>
    <li style="margin-bottom: 8px;"><b>Structured Organization:</b> Medical entities such as symptoms, medical histories, allergies, and vital signs organized into nodes, interlinked by edges depicting relationships (e.g., <code style="background-color: #f1f3f4; padding: 2px 4px; border-radius: 4px; font-size: 0.9em; color: #d81b60;">HAS_SYMPTOM</code>).</li>
    <li style="margin-bottom: 8px;"><b>LLM-based NER:</b> Utilizes advanced NER techniques to transform unstructured clinical notes into structured data.</li>
    <li><b>Graph Database:</b> Efficiently stored and queried using Neo4j for complex relationship analysis.</li>
  </ul>
</div>

<h3 style="color: #202124; margin-top: 1.5em; margin-bottom: 0.8em; font-weight: 500;">2. Reasoning Retrieval-Augmented Generation Workflow</h3>

<p style="color: #3c4043;">This multi-agent system provides a dynamic method for processing natural language queries and generating context-appropriate responses across three primary stages:</p>

<div style="display: flex; flex-direction: column; gap: 12px; margin-bottom: 2em; margin-top: 1em;">
  <div style="background-color: white; border-left: 4px solid #4285f4; padding: 16px; border-radius: 4px; box-shadow: 0 1px 2px rgba(0,0,0,0.1);">
    <h4 style="color: #1a73e8; margin-top: 0; margin-bottom: 8px; font-size: 1.1em;"><i class="fas fa-search" style="margin-right: 8px;"></i>Retrieval Stage</h4>
    <ul style="margin: 0; padding-left: 20px; color: #5f6368; font-size: 0.95em;">
      <li><b>Retrieval Agent:</b> Selects relevant nodes and relationships from the AIPatient KG based on queries.</li>
      <li><b>KG Query Generation Agent:</b> Formulates Cypher queries to extract pertinent information.</li>
    </ul>
  </div>

  <div style="background-color: white; border-left: 4px solid #fbbc05; padding: 16px; border-radius: 4px; box-shadow: 0 1px 2px rgba(0,0,0,0.1);">
    <h4 style="color: #d93025; margin-top: 0; margin-bottom: 8px; font-size: 1.1em;"><i class="fas fa-brain" style="margin-right: 8px;"></i>Reasoning Stage</h4>
    <ul style="margin: 0; padding-left: 20px; color: #5f6368; font-size: 0.95em;">
      <li><b>Abstraction Agent:</b> Simplifies and rephrases user queries into more general forms.</li>
      <li><b>Checker Agent:</b> Verifies alignment between retrieved information and user inquiries.</li>
    </ul>
  </div>

  <div style="background-color: white; border-left: 4px solid #34a853; padding: 16px; border-radius: 4px; box-shadow: 0 1px 2px rgba(0,0,0,0.1);">
    <h4 style="color: #188038; margin-top: 0; margin-bottom: 8px; font-size: 1.1em;"><i class="fas fa-comment-dots" style="margin-right: 8px;"></i>Generation Stage</h4>
    <ul style="margin: 0; padding-left: 20px; color: #5f6368; font-size: 0.95em;">
      <li><b>Rewrite Agent:</b> Transforms KG results into natural language with simulated patient personality traits.</li>
      <li><b>Summarization Agent:</b> Updates and maintains context for multi-turn interactions.</li>
    </ul>
  </div>
</div>

<h2 style="color: #1a73e8; border-bottom: 2px solid #e8eaed; padding-bottom: 10px; margin-top: 2em; margin-bottom: 1em; font-weight: 500;">💻 Technical Specifications</h2>

<div style="background-color: white; border: 1px solid #e8eaed; border-radius: 8px; overflow: hidden; box-shadow: 0 1px 3px rgba(0,0,0,0.06); margin-bottom: 2em;">
  <div style="padding: 20px; border-bottom: 1px solid #e8eaed; background-color: #f8f9fa;">
    <h3 style="color: #1a73e8; margin: 0 0 10px 0; font-weight: 500; font-size: 1.2em;"><i class="fas fa-project-diagram mr-2"></i>Named Entity Recognition (NER) & Database</h3>
    <ul style="margin-bottom: 0; color: #3c4043; padding-left: 20px;">
      <li>LLM-based NER system for extracting medical entities from unstructured discharge summary data.</li>
      <li>Establishes distinct relationships (e.g., "HAS_FAMILY_MEMBER") within the graph.</li>
      <li>Hosted in <b>Neo4j</b> for complex multi-faceted relationship queries instead of linear retrieval.</li>
      <li>Utilizes <b>Cypher Query Language</b> to navigate graph functionalities efficiently.</li>
    </ul>
  </div>
  <div style="padding: 20px;">
    <h3 style="color: #1a73e8; margin: 0 0 10px 0; font-weight: 500; font-size: 1.2em;"><i class="fas fa-chart-line mr-2"></i>Performance Evaluation</h3>
    <ul style="margin-bottom: 0; color: #3c4043; padding-left: 20px;">
      <li><b>Ablation Studies:</b> Configurations using Retrieval & Abstraction Agents significantly outperformed simpler setups.</li>
      <li><b>Overall QA Accuracy:</b> 94.15% in EHR-based medical Question Answering.</li>
      <li><b>Readability Metrics:</b> Median Flesch Reading Ease (77.23) & M. Flesch-Kincaid Grade Level (5.6).</li>
      <li><b>Robustness & Stability:</b> ANOVA F-value 0.6126 (p>0.1) and 0.782 (p>0.1) respectively.</li>
    </ul>
  </div>
</div>

<h2 style="color: #1a73e8; border-bottom: 2px solid #e8eaed; padding-bottom: 10px; margin-top: 2em; margin-bottom: 1em; font-weight: 500;">🌟 Key Contributions</h2>

<div style="background-color: white; border: 1px solid #e8eaed; border-radius: 8px; padding: 20px; box-shadow: 0 1px 3px rgba(0,0,0,0.06); margin-bottom: 2em;">
  <ul style="list-style: none; padding-left: 0; margin: 0;">
    <li style="margin-bottom: 12px; display: flex; align-items: flex-start;">
      <span style="color: #34a853; margin-right: 12px; font-size: 1.2em;">✓</span>
      <div><b>Advanced Knowledge Graph:</b> AIPatient KG provides a robust foundation with high validity (F1 0.89) derived from real EHR data.</div>
    </li>
    <li style="margin-bottom: 12px; display: flex; align-items: flex-start;">
      <span style="color: #34a853; margin-right: 12px; font-size: 1.2em;">✓</span>
      <div><b>Multi-Agent Architecture:</b> Six specialized LLM agents working in concert for comprehensive patient simulation.</div>
    </li>
    <li style="margin-bottom: 12px; display: flex; align-items: flex-start;">
      <span style="color: #34a853; margin-right: 12px; font-size: 1.2em;">✓</span>
      <div><b>Superior Performance:</b> 94.15% accuracy outperforming existing benchmarks.</div>
    </li>
    <li style="margin-bottom: 12px; display: flex; align-items: flex-start;">
      <span style="color: #34a853; margin-right: 12px; font-size: 1.2em;">✓</span>
      <div><b>High Readability:</b> Ensures accessible communication for educational purposes.</div>
    </li>
    <li style="display: flex; align-items: flex-start;">
      <span style="color: #34a853; margin-right: 12px; font-size: 1.2em;">✓</span>
      <div><b>Robustness and Stability:</b> Consistent performance across varied scenarios and question formulations.</div>
    </li>
  </ul>
</div>

<h2 style="color: #1a73e8; border-bottom: 2px solid #e8eaed; padding-bottom: 10px; margin-top: 2em; margin-bottom: 1em; font-weight: 500;">🚀 Applications and Impact</h2>

<p style="color: #3c4043; font-size: 1.05em; margin-bottom: 1.5em;">The AIPatient framework offers transformative potential for:</p>

<div class="d-flex flex-wrap" style="gap: 12px; margin-bottom: 2em;">
  <span style="background-color: #e8f0fe; color: #1967d2; padding: 8px 16px; border-radius: 20px; font-size: 0.95em; font-weight: 500;"><i class="fas fa-user-md mr-1"></i> Medical Education</span>
  <span style="background-color: #fce8e6; color: #c5221f; padding: 8px 16px; border-radius: 20px; font-size: 0.95em; font-weight: 500;"><i class="fas fa-stethoscope mr-1"></i> Clinical Decision-Making</span>
  <span style="background-color: #e6f4ea; color: #137333; padding: 8px 16px; border-radius: 20px; font-size: 0.95em; font-weight: 500;"><i class="fas fa-microscope mr-1"></i> Research & Evaluation</span>
  <span style="background-color: #fef7e0; color: #b06000; padding: 8px 16px; border-radius: 20px; font-size: 0.95em; font-weight: 500;"><i class="fas fa-book-open mr-1"></i> Curriculum Development</span>
</div>

<h2 style="color: #1a73e8; border-bottom: 2px solid #e8eaed; padding-bottom: 10px; margin-top: 2em; margin-bottom: 1em; font-weight: 500;">🔮 Future Directions</h2>

<div style="display: grid; grid-template-columns: repeat(auto-fit, minmax(250px, 1fr)); gap: 16px; margin-bottom: 2em;">
  <div style="background-color: #f8f9fa; border-radius: 8px; padding: 16px; border-left: 4px solid #1a73e8;">
    <h4 style="margin-top: 0; color: #202124; font-size: 1.05em;"><i class="fas fa-database" style="color: #1a73e8; margin-right: 8px;"></i> Broader Data Scope</h4>
    <p style="margin-bottom: 0; font-size: 0.95em; color: #5f6368;">Incorporating wider variety of healthcare scenarios for more extensive knowledge bases.</p>
  </div>
  <div style="background-color: #f8f9fa; border-radius: 8px; padding: 16px; border-left: 4px solid #34a853;">
    <h4 style="margin-top: 0; color: #202124; font-size: 1.05em;"><i class="fas fa-photo-video" style="color: #34a853; margin-right: 8px;"></i> Multimodal Integration</h4>
    <p style="margin-bottom: 0; font-size: 0.95em; color: #5f6368;">Adding medical imaging and other data modalities to simulate full clinical inputs.</p>
  </div>
  <div style="background-color: #f8f9fa; border-radius: 8px; padding: 16px; border-left: 4px solid #fbbc05;">
    <h4 style="margin-top: 0; color: #202124; font-size: 1.05em;"><i class="fas fa-hospital" style="color: #fbbc05; margin-right: 8px;"></i> Real-time Clinical</h4>
    <p style="margin-bottom: 0; font-size: 0.95em; color: #5f6368;">Adapting environments for live clinical settings and interactive deployment.</p>
  </div>
  <div style="background-color: #f8f9fa; border-radius: 8px; padding: 16px; border-left: 4px solid #ea4335;">
    <h4 style="margin-top: 0; color: #202124; font-size: 1.05em;"><i class="fas fa-chalkboard-teacher" style="color: #ea4335; margin-right: 8px;"></i> Enhanced Training</h4>
    <p style="margin-bottom: 0; font-size: 0.95em; color: #5f6368;">Further enriching educational landscapes and outcomes for healthcare professionals.</p>
  </div>
</div>

<h2 style="color: #1a73e8; border-bottom: 2px solid #e8eaed; padding-bottom: 10px; margin-top: 2em; margin-bottom: 1em; font-weight: 500;">📝 Conclusion</h2>

The AIPatient framework exemplifies a transformative approach to patient simulation through EHR data and LLM-powered interactions, emphasizing structured retrieval and knowledge dissemination in a manner conducive to enhancing medical training and decision-making processes. By embedding these systems within medical curricula and research protocols, we propose significant advancements in how interactions with simulated patients can impact educational outcomes and clinical preparedness.

---

<h2 style="color: #1a73e8; border-bottom: 2px solid #e8eaed; padding-bottom: 10px; margin-top: 2em; margin-bottom: 1em; font-weight: 500;">📖 Welcome to Cite Our Article</h2>

If you find our work helpful, please consider citing it:

<div style="background-color: #f8f9fa; border: 1px solid #e1e4e8; border-radius: 8px; margin-top: 1.5em; overflow: hidden; box-shadow: 0 2px 8px rgba(0,0,0,0.05); max-width: 100%;">
  <div style="background-color: #f1f3f4; padding: 10px 16px; border-bottom: 1px solid #e1e4e8; display: flex; justify-content: space-between; align-items: center;">
    <span style="color: #5f6368; font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Helvetica, Arial, sans-serif; font-size: 0.85em; font-weight: 600; text-transform: uppercase; letter-spacing: 0.5px;">BibTeX</span>
  </div>
  <div style="padding: 20px; overflow-x: auto;">
<pre style="margin: 0; background: transparent; border: none; padding: 0;"><code style="font-family: 'SFMono-Regular', Consolas, 'Liberation Mono', Menlo, Courier, monospace; font-size: 0.95em; line-height: 1.5; color: #24292e;">@ARTICLE{Yu2025-tb,
  title     = "Simulated patient systems powered by large language model-based
               {AI} agents offer potential for transforming medical education",
  author    = "Yu, Huizi and Zhou, Jiayan and Li, Lingyao and Chen, Shan and
               Gallifant, Jack and Shi, Anye and Sun, Jie and Li, Xiang and He,
               Jingxian and Hua, Wenyue and Jin, Mingyu and Chen, Guang and
               Zhou, Yang and Li, Zhao and Gupte, Trisha and Chen, Ming-Li and
               Azizi, Zahra and Dou, Qi and Yan, Bryan P and Xing, Yanqiu and
               Zhang, Yongfeng and Assimes, Themistocles L and Bitterman,
               Danielle S and Ma, Xin and Lu, Lin and Fan, Lizhou",
  journal   = "Commun. Med. (Lond.)",
  publisher = "Springer Science and Business Media LLC",
  volume    =  6,
  number    =  1,
  pages     =  27,
  month     =  dec,
  year      =  2025,
  language  = "en"
}</code></pre>
  </div>
</div>