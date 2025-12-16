# NER End-to-End Tutorial

A comprehensive Jupyter notebook course teaching Named Entity Recognition (NER) from fundamentals to production deployment.

## Course Overview

This course covers NER end-to-end with 11 detailed lessons:

| Lesson | Topic | Description |
|--------|-------|-------------|
| 01 | [NER Fundamentals](notebooks/01_NER_Fundamentals_First_Principles.ipynb) | First principles, BIO tagging, entity types |
| 02 | [spaCy NER](notebooks/02_Traditional_NER_with_spaCy.ipynb) | Traditional NER with spaCy pipelines |
| 03 | [BERT NER](notebooks/03_BERT_NER_with_Transformers.ipynb) | Token classification with Transformers |
| 04 | [GLiNER](notebooks/04_GLiNER_Zero_Shot_NER.ipynb) | Zero-shot NER for custom entities |
| 05 | [Fine-tuning](notebooks/05_Fine_Tuning_NER_Models.ipynb) | Training custom NER models |
| 06 | [Advanced NER](notebooks/06_Advanced_NER_NuNER_Comparisons.ipynb) | NuNER, model comparisons, unified pipelines |
| 07 | [Production](notebooks/07_NER_Evaluation_Production.ipynb) | Evaluation, APIs, monitoring |
| 08 | [SpanMarker](notebooks/08_SpanMarker_NER.ipynb) | SOTA span-based NER (93.1 F1 on CoNLL03) |
| 09 | [LLM-based NER](notebooks/09_LLM_Based_NER.ipynb) | GPT-4, Claude, Llama for NER |
| 10 | [UniversalNER](notebooks/10_UniversalNER_UniNER.ipynb) | LLM-distilled open-domain NER |
| 11 | [Flair NER](notebooks/11_Flair_NER.ipynb) | Contextual string embeddings |

## Quick Start

### Run on Google Colab

Each notebook can be run directly on Google Colab. Just open the notebook and click "Open in Colab" or upload it to your Google Drive.

### Local Installation

```bash
# Clone the repository
git clone https://github.com/AJ-appz/NER-E2E.git
cd NER-E2E

# Install dependencies (each notebook also has !pip install commands)
pip install transformers datasets spacy gliner seqeval evaluate torch flair span-marker
python -m spacy download en_core_web_sm
```

## What You'll Learn

### Fundamentals
- What NER is and why it matters
- BIO/IOB tagging schemes
- Entity types and annotation formats
- Evolution of NER approaches

### Models Covered
- **spaCy**: Fast, production-ready NLP
- **BERT**: Transformer-based token classification
- **GLiNER**: Zero-shot NER (any entity type without training)
- **NuNER**: Advanced zero-shot with longer entity support
- **SpanMarker**: State-of-the-art span-based NER
- **LLMs**: GPT-4, Claude, Llama for NER tasks
- **UniversalNER**: LLM-distilled open-domain NER
- **Flair**: Contextual string embeddings

### Practical Skills
- Fine-tuning BERT for custom NER
- Handling subword tokenization
- Evaluation with seqeval metrics
- Building production NER services
- Error analysis and debugging
- LLM prompting for entity extraction
- Hybrid pipeline architectures

## Key Concepts

### Tagging Scheme (BIO)

```
Sentence: "Barack Obama visited Paris"
Tags:     B-PER   I-PER    O       B-LOC

B- = Beginning of entity
I- = Inside entity (continuation)
O  = Outside any entity
```

### Model Selection Guide

```
Need standard entities (PER, ORG, LOC)?
├── Yes → Use spaCy, BERT, or SpanMarker
└── No (custom entities)
    ├── Have training data?
    │   ├── Yes → Fine-tune BERT or SpanMarker
    │   └── No → Use GLiNER, NuNER, or UniversalNER
    └── Need highest zero-shot quality?
        ├── Speed priority → GLiNER
        ├── Quality priority → UniversalNER
        └── Rare entity types → LLM-based (GPT-4/Claude)
```

## Resources & References

### Papers
- [BERT (Devlin et al., 2019)](https://arxiv.org/abs/1810.04805)
- [GLiNER (Zaratiana et al., 2023)](https://arxiv.org/abs/2311.08526)
- [NuNER (NuMind, 2024)](https://arxiv.org/abs/2402.15343)
- [SpanMarker (Aarsen, 2023)](https://arxiv.org/abs/2304.11498)
- [UniversalNER (Zhou et al., 2023)](https://arxiv.org/abs/2308.03279)
- [Flair Embeddings (Akbik et al., 2018)](https://aclanthology.org/C18-1139/)
- [GPT-NER (Wang et al., 2023)](https://arxiv.org/abs/2304.10428)

### Documentation
- [Hugging Face Token Classification](https://huggingface.co/docs/transformers/tasks/token_classification)
- [spaCy EntityRecognizer](https://spacy.io/api/entityrecognizer)
- [GLiNER GitHub](https://github.com/urchade/GLiNER)
- [SpanMarker GitHub](https://github.com/tomaarsen/SpanMarkerNER)
- [Flair GitHub](https://github.com/flairNLP/flair)
- [seqeval](https://github.com/chakki-works/seqeval)

### Datasets
- [CoNLL-2003](https://huggingface.co/datasets/eriktks/conll2003)
- [WNUT-17](https://huggingface.co/datasets/wnut_17)
- [OntoNotes 5.0](https://catalog.ldc.upenn.edu/LDC2013T19)
- [FewNERD](https://ningding97.github.io/fewnerd/)

## License

MIT License - feel free to use for learning and commercial projects.

## Contributing

Contributions welcome! Please open an issue or PR.
