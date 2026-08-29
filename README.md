<h1 align="center">
<img src="images/L-NLP_Logo_Transparent.png" width="100" alt="L-NLP" />
<br>
AILQA: Evaluating AI-Driven Legal Question Answering Systems for the Indian Legal System <br> <a href="https://link.springer.com/journal/10506">AI and Law Journal</a> </strong>
 </h1>
<p align="center">
  <b>Retrieval-Augmented Generation and Large Language Models for Indian Legal Question Answering</b>
</p>
<p align="center">
  <a href="https://huggingface.co/L-NLProc"><b>[🌐 Website]</b></a> •
  <a href=""><b>[📜 Proceedings]</b></a> •
  <a href="https://arxiv.org/abs/2607.18825"><b>[📜 ArXiv]</b></a> •
  <a href="https://huggingface.co/L-NLProc/"><b>[🤗 HF Models]</b></a> •
  <a href="https://github.com/ShubhamKumarNigam/AILQA/tree/main"><b>[<img src="images/icons8-github-16.png" alt="Github" /> GitHub]</b></a> •
  <a href="https://github.com/ShubhamKumarNigam/AILQA/tree/main"><b>[📝Dataset Access in the GitHub repository]</b></a> 
</p>
    
</p>
<p align="center">
 <b>Authors:</b> <a href="https://sites.google.com/view/shubhamkumarnigam">Shubham Kumar Nigam</a>, <a>Shubham Kumar Mishra</a>, <a href="https://www.linkedin.com/in/noelshallum/">Noel Shallum</a>, <a href="https://sites.google.com/view/kripabandhughosh-homepage/home">Kripabandhu Ghosh</a>, and <a href="https://www.cse.iitk.ac.in/users/arnabb/">Arnab Bhattacharya</a>
</p>

---

## Overview

**AILQA** is a comprehensive study of AI-driven **Legal Question Answering (QA) for the Indian legal system**. We investigate how Large Language Models (LLMs), embedding models, and **Retrieval-Augmented Generation (RAG)** can improve the accuracy, relevance, and reliability of answers to Indian legal questions.

The study evaluates multiple embedding and generative models using **lexical, semantic, human-expert, LLM-based, and statistical evaluation**, together with performance on the **All India Bar Examination (AIBE)**.

> **Main takeaway:** RAG can improve legal QA, but its effectiveness strongly depends on retrieving **relevant, concise, and legally appropriate context**.

---
<h1 align="center">
<img src="images/Overview Image.png" width="700" alt="Overview" />
</h1>

## Why This Matters

Indian legal information is often lengthy, complex, and distributed across statutes, judgments, and legal commentary.

AILQA investigates whether AI can:

- improve access to legal information;
- assist legal professionals and law students;
- provide more contextual and informative legal responses;
- reduce unsupported or hallucinated legal information through retrieval.

---

## Dataset

AILQA uses approximately **7,221 Indian legal documents**:

| Data | Documents |
|---|---:|
| Supreme Court Judgments | 6,942 |
| Acts | 15 |
| Legal Articles | 264 |
| **Total** | **7,221** |

### Evaluation Sets

- **Test Set 1:** 50 legal queries
- **Test Set 2:** 100 legal QA pairs across:
  - Anticipatory Bail
  - Criminal Law
  - Cyber Crime
  - Juvenile Issues
  - Sex Crimes
- **AIBE Benchmark:** 1,158 multiple-choice questions

---

## Models

### Embedding Models

- OpenAI Ada
- Instructor-XL
- Mxbai

### Generative Models

- Davinci
- Flan-UL2
- Llama2-70B
- GPT-3.5 Turbo
- Llama3-70B
- Mixtral-8x7B

---

## AILQA Pipeline

```text
Legal Documents
      ↓
Preprocessing & Chunking
      ↓
Embedding Generation
      ↓
ChromaDB Vector Store
      ↓
Top Relevant Legal Context
      ↓
Question + Retrieved Context
      ↓
Large Language Model
      ↓
Legal Answer
      ↓
Comprehensive Evaluation
```

The RAG baseline uses embedding-based cosine similarity to retrieve relevant legal passages before answer generation.

---

## Evaluation

AILQA combines multiple evaluation perspectives:

- **Lexical:** ROUGE-1, ROUGE-2, ROUGE-L, BLEU
- **Semantic:** MPNET similarity
- **Human:** Legal expert ratings on a 1–5 scale
- **Automatic:** LLM-based evaluation
- **Statistical:** Pairwise significance testing
- **Practical Benchmark:** All India Bar Examination

---

## Key Findings

- **RAG does not universally improve every model.**
- Models with weaker prior knowledge can benefit substantially from retrieved context.
- Irrelevant retrieval can reduce performance and introduce hallucinations.
- Retrieval quality is therefore as important as generation quality.
- Lexical metrics alone are insufficient for evaluating legal answers.

### Selected Results

| Result | Best Performance |
|---|---:|
| Test Set 1 Expert Rating | **Davinci + Ada: 3.74 / 5** |
| Test Set 2 Expert Rating | **Mixtral-8x7B: 4.59 / 5** |
| Test Set 2 Semantic Score | **Llama3-70B: 0.65** |
| AIBE Accuracy | **Llama3-70B + RAG: 71.13%** |

A notable improvement was observed for **Llama2-70B on AIBE**, increasing from **45.72% to 51.69%** with RAG.

---

## Contributions

- Introduces a RAG-based framework for **Indian Legal Question Answering**.
- Evaluates multiple embedding–LLM combinations.
- Provides a comprehensive multi-dimensional evaluation methodology.
- Studies both the **benefits and failure modes of RAG**.
- Analyzes hallucinations caused by missing or irrelevant legal context.
- Benchmarks models on real-world legal questions and the AIBE dataset.
- Supports reproducible research in Indian Legal NLP.

---

## Impact

AILQA can contribute toward:

- improved public access to legal information;
- AI-assisted legal research;
- legal education and bar examination preparation;
- more transparent legal decision-support tools;
- development of reliable and responsible Legal AI systems for India.

---

## Limitations

- The study primarily focuses on **Indian criminal law**.
- Expert evaluation covers a limited sample.
- The current RAG architecture uses relatively simple dense retrieval.
- Irrelevant context can negatively affect otherwise capable LLMs.
- Legal information changes over time and requires continuous updating.

AILQA should therefore be considered a **research and decision-support prototype**, not a substitute for professional legal advice.

---

## Future Work

Future extensions include:

- larger and more diverse Indian legal QA datasets;
- hybrid lexical + semantic retrieval;
- neural reranking;
- authority- and metadata-aware legal retrieval;
- version-aware retrieval for changing laws;
- citation-grounded answer generation;
- improved hallucination detection;
- broader blinded evaluation with practising legal professionals.

---

## Citation

If you use AILQA in your research, please cite:

```bibtex
@article{nigam2026ailqa,
  title={AILQA: Evaluating AI-Driven Legal Question Answering Systems for the Indian Legal System},
  author={Nigam, Shubham Kumar and Mishra, Shubham Kumar and Shallum, Noel and Ghosh, Kripabandhu and Bhattacharya, Arnab},
  journal={arXiv preprint arXiv:2607.18825},
  year={2026}
}
```

---

## Contact

For questions, suggestions, or collaboration:

- 📧 `shubhamkumarnigam@gmail.com`
- 🐛 [Open a GitHub Issue](https://github.com/ShubhamKumarNigam/AILQA/issues)

---

## Disclaimer

This repository is intended for **research and educational purposes**. AI-generated legal responses should be independently verified using authoritative legal sources and qualified legal professionals.


