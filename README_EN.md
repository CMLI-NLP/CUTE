# CUTE: A Multilingual Dataset for Enhancing Cross-Lingual Knowledge Transfer in Low-Resource Languages

<div align="center">

[![Paper](https://img.shields.io/badge/Paper-PDF-red)](https://aclanthology.org/2025.coling-main.670/)
[![Conference](https://img.shields.io/badge/COLING-2025-blue)](https://aclanthology.org/2025.coling-main.670/)
[![Dataset](https://img.shields.io/badge/🤗-Dataset-yellow)](https://huggingface.co/datasets/CMLI-NLP/CUTE-Datasets)
[![Model](https://img.shields.io/badge/🤗-Model-green)](https://huggingface.co/CMLI-NLP/CUTE-Llama)

English | [简体中文](README.md)

</div>

## 📝 Overview

CUTE (Chinese, Uyghur, Tibetan, English) is a large-scale multilingual dataset designed to enhance cross-lingual knowledge transfer for low-resource languages. Additionally, we have trained and open-sourced the CUTE-Llama language model based on this dataset.

Paper Link: [CUTE: A Multilingual Dataset for Enhancing Cross-Lingual Knowledge Transfer in Low-Resource Languages](https://aclanthology.org/2025.coling-main.670/)

## 🔗 Resources

### Dataset
- HuggingFace: [CMLI-NLP/CUTE-Datasets](https://huggingface.co/datasets/CMLI-NLP/CUTE-Datasets)
  - Parallel Corpus: [parallel-corpus](https://huggingface.co/datasets/CMLI-NLP/CUTE-Datasets/tree/main/parallel-corpus)
  - Non-parallel Corpus: [non-parallel-corpus](https://huggingface.co/datasets/CMLI-NLP/CUTE-Datasets/tree/main/non-parallel-corpus)

### Model
- HuggingFace: [CMLI-NLP/CUTE-Llama](https://huggingface.co/CMLI-NLP/CUTE-Llama)
  - CUTE-Llama-P: [CUTE-Llama-Parallel](https://huggingface.co/CMLI-NLP/CUTE-Llama/tree/main/CUTE-Llama-Parallel)
  - CUTE-Llama-NP: [CUTE-Llama-Non-Parallel](https://huggingface.co/CMLI-NLP/CUTE-Llama/tree/main/CUTE-Llama-Non-Parallel)

## 📊 Dataset Details

### Overview
The CUTE dataset consists of two corpora:
- **Parallel Corpus**: Four languages with 99.98% content parallelism
- **Non-parallel Corpus**: English content identical to the parallel corpus, while other languages differ

### Data Scale

<details open>
<summary><b>Parallel Corpus (CUTE-P)</b></summary>

| Language | Lines | Size(GB) |
|:-----:|:------:|:---------:|
| Chinese | 933,946 | 2.62 |
| English | 933,989 | 3.49 |
| Uyghur | 934,002 | 7.37 |
| Tibetan | 934,140 | 11.22 |
| **Total** | **3,736,077** | **24.70** |

</details>

<details open>
<summary><b>Non-parallel Corpus (CUTE-NP)</b></summary>

| Language | Lines | Size(GB) |
|:-----:|:------:|:---------:|
| Chinese | 1,000,609 | 2.64 |
| English | 933,989 | 3.49 |
| Uyghur | 1,010,381 | 7.77 |
| Tibetan | 989,723 | 11.90 |
| **Total** | **3,934,702** | **25.80** |

</details>

### Data Quality

Our human evaluation of machine translation quality shows:
- Chinese-English translation average score: 9.1
- Chinese-Uyghur translation average score: 8.5
- Chinese-Tibetan translation average score: 8.6

### Usage Notes

#### Important Notes about Parallel Corpus:

**1. Sentence-level Alignment Limitations**
- As shown in the CUTE-P column of Table 2 in our paper, the four languages have slightly different line counts in their txt files
- This is due to occasional inconsistencies in translation line numbers during machine translation (e.g., one line of Chinese may be translated into two lines of Uyghur)
- Therefore, we can only achieve **document-level parallelism**, not strict **sentence-level parallelism**

**2. Content Alignment Characteristics**
- The overall parallelism of documents across the four languages reaches **99.98%**
- Sentence order may be disrupted, but this does not affect the pre-training of large language models
- Our experiments did not perform sentence-level parallel processing for the four languages, achieving parallelism only at the document level

> 💡 **Note**: This dataset is primarily designed for multilingual pre-training rather than sentence-level translation tasks.

## 🤖 Model Description

### CUTE-Llama

CUTE-Llama is a multilingual model based on the Llama2-7B architecture. We provide two versions:
- **CUTE-Llama-P**: Trained using parallel corpus
- **CUTE-Llama-NP**: Trained using non-parallel corpus

### Key Features

- ✨ Extended vocabulary for Chinese, Uyghur, and Tibetan
- 🎯 Optimized for low-resource languages
- 🔄 Support for cross-lingual knowledge transfer

## 📚 Citation

If you use our dataset or model, please cite our paper:

```bibtex
@inproceedings{zhuang2025cute,
  title={CUTE: A Multilingual Dataset for Enhancing Cross-Lingual Knowledge Transfer in Low-Resource Languages},
  author={Zhuang, Wenhao and Sun, Yuan},
  booktitle={Proceedings of the 31st International Conference on Computational Linguistics},
  pages={10037--10046},
  year={2025}
}
```
