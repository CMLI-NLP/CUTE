# CUTE Dataset & CUTE-Llama

[English](README_EN.md) | 简体中文

CUTE (Chinese, Uyghur, Tibetan, English) 是一个包含中文、维吾尔语、藏语和英语的大规模多语言数据集，旨在增强低资源语言的跨语言知识迁移。同时，我们也基于该数据集训练并开源了相应的语言模型CUTE-Llama。

## 数据集介绍

### 概述

CUTE数据集包含两组语料：
- **平行语料**：四种语言在内容上具有99.98%的平行性
- **非平行语料**：除英语部分与平行语料相同外，其他语言的内容均不同

### 数据规模

#### 平行语料 (CUTE-P)
| 语言 | 行数 | 大小(GB) |
|-----|------|---------|
| 中文 | 933,946 | 2.62 |
| 英语 | 933,989 | 3.49 |
| 维吾尔语 | 934,002 | 7.37 |
| 藏语 | 934,140 | 11.22 |
| 总计 | 3,736,077 | 24.70 |

#### 非平行语料 (CUTE-NP)
| 语言 | 行数 | 大小(GB) |
|-----|------|---------|
| 中文 | 1,000,609 | 2.64 |
| 英语 | 933,989 | 3.49 |
| 维吾尔语 | 1,010,381 | 7.77 |
| 藏语 | 989,723 | 11.90 |
| 总计 | 3,934,702 | 25.80 |

### 数据质量

我们通过人工评估验证了机器翻译的质量。评估结果显示：
- 中英翻译平均得分：9.1分
- 中维翻译平均得分：8.5分
- 中藏翻译平均得分：8.6分

## 模型介绍

CUTE-Llama 是基于 Llama2-7B 架构开发的多语言模型，我们提供了两个版本：
- **CUTE-Llama-P**：使用平行语料训练的版本
- **CUTE-Llama-NP**：使用非平行语料训练的版本

### 主要特点
- 扩展了中文、维吾尔语和藏语的词表
- 针对低资源语言进行了优化
- 支持跨语言知识迁移

## 模型效果

在多个下游任务中，CUTE-Llama表现出色：

### 文本分类任务 (准确率/F1值)
- 中文：90.25/90.17
- 藏语：51.08/48.46
- 维吾尔语：87.0/89.08

### 机器翻译任务 (BLEU分数)
- 中文到藏语：9.5
- 中文到维吾尔语：10.2

## 开源地址

### 数据集
- HuggingFace: [CMLI-NLP/CUTE-Datasets](https://huggingface.co/datasets/CMLI-NLP/CUTE-Datasets)
  - 平行语料：[parallel-corpus](https://huggingface.co/datasets/CMLI-NLP/CUTE-Datasets/tree/main/parallel-corpus)
  - 非平行语料：[non-parallel-corpus](https://huggingface.co/datasets/CMLI-NLP/CUTE-Datasets/tree/main/non-parallel-corpus)

### 模型
- HuggingFace: [CMLI-NLP/CUTE-Llama](https://huggingface.co/CMLI-NLP/CUTE-Llama)
  - CUTE-Llama-P：[CUTE-Llama-Parallel](https://huggingface.co/CMLI-NLP/CUTE-Llama/tree/main/CUTE-Llama-Parallel)
  - CUTE-Llama-NP：[CUTE-Llama-Non-Parallel](https://huggingface.co/CMLI-NLP/CUTE-Llama/tree/main/CUTE-Llama-Non-Parallel)

## 引用

如果您使用了我们的数据集或模型，请引用我们的论文：

```bibtex
@inproceedings{zhuang-sun-2025-cute,
    title = "{CUTE}: A Multilingual Dataset for Enhancing Cross-Lingual Knowledge Transfer in Low-Resource Languages",
    author = "Zhuang, Wenhao  and
      Sun, Yuan",
    booktitle = "Proceedings of the 31st International Conference on Computational Linguistics",
    month = jan,
    year = "2025",
    address = "Abu Dhabi, UAE",
    publisher = "Association for Computational Linguistics",
    url = "https://aclanthology.org/2025.coling-main.670/",
    pages = "10037--10046"
}
```
