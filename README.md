# CUTE: A Multilingual Dataset for Enhancing Cross-Lingual Knowledge Transfer in Low-Resource Languages

<div align="center">

[![Paper](https://img.shields.io/badge/Paper-PDF-red)](https://aclanthology.org/2025.coling-main.670/)
[![Conference](https://img.shields.io/badge/COLING-2025-blue)](https://aclanthology.org/2025.coling-main.670/)
[![Dataset](https://img.shields.io/badge/🤗-Dataset-yellow)](https://huggingface.co/datasets/CMLI-NLP/CUTE-Datasets)
[![Model](https://img.shields.io/badge/🤗-Model-green)](https://huggingface.co/CMLI-NLP/CUTE-Llama)

[English](README_EN.md) | 简体中文

</div>

## 📝 概述

CUTE (Chinese, Uyghur, Tibetan, English) 是一个包含中文、维吾尔语、藏语和英语的大规模多语言数据集，旨在增强低资源语言的跨语言知识迁移。同时，我们也基于该数据集训练并开源了相应的语言模型CUTE-Llama。

论文链接：[CUTE: A Multilingual Dataset for Enhancing Cross-Lingual Knowledge Transfer in Low-Resource Languages](https://aclanthology.org/2025.coling-main.670/)

## 🔗 开源地址

### 数据集
- HuggingFace: [CMLI-NLP/CUTE-Datasets](https://huggingface.co/datasets/CMLI-NLP/CUTE-Datasets)
  - 平行语料：[parallel-corpus](https://huggingface.co/datasets/CMLI-NLP/CUTE-Datasets/tree/main/parallel-corpus)
  - 非平行语料：[non-parallel-corpus](https://huggingface.co/datasets/CMLI-NLP/CUTE-Datasets/tree/main/non-parallel-corpus)

### 模型
- HuggingFace: [CMLI-NLP/CUTE-Llama](https://huggingface.co/CMLI-NLP/CUTE-Llama)
  - CUTE-Llama-P：[CUTE-Llama-Parallel](https://huggingface.co/CMLI-NLP/CUTE-Llama/tree/main/CUTE-Llama-Parallel)
  - CUTE-Llama-NP：[CUTE-Llama-Non-Parallel](https://huggingface.co/CMLI-NLP/CUTE-Llama/tree/main/CUTE-Llama-Non-Parallel)

## 📊 数据集介绍

### 概述

CUTE数据集包含两组语料：
- **平行语料**：四种语言在内容上具有99.98%的平行性
- **非平行语料**：除英语部分与平行语料相同外，其他语言的内容均不同

### 数据规模

<details open>
<summary><b>平行语料 (CUTE-P)</b></summary>

| 语言 | 行数 | 大小(GB) |
|:-----:|:------:|:---------:|
| 中文 | 933,946 | 2.62 |
| 英语 | 933,989 | 3.49 |
| 维吾尔语 | 934,002 | 7.37 |
| 藏语 | 934,140 | 11.22 |
| **总计** | **3,736,077** | **24.70** |

</details>

<details open>
<summary><b>非平行语料 (CUTE-NP)</b></summary>

| 语言 | 行数 | 大小(GB) |
|:-----:|:------:|:---------:|
| 中文 | 1,000,609 | 2.64 |
| 英语 | 933,989 | 3.49 |
| 维吾尔语 | 1,010,381 | 7.77 |
| 藏语 | 989,723 | 11.90 |
| **总计** | **3,934,702** | **25.80** |

</details>

### 数据质量

我们通过人工评估验证了机器翻译的质量。评估结果显示：
- 中英翻译平均得分：9.1分 
- 中维翻译平均得分：8.5分
- 中藏翻译平均得分：8.6分

### 使用说明

#### 关于平行语料的重要提醒：

**1. 句对级对齐限制**
- 如论文中Table 2的CUTE-P列所示，四种语言的txt文件行数略有不同
- 这是由于机器翻译过程中偶现的翻译行数不一致导致的（例如：一行中文可能翻译成两行维吾尔语）
- 因此目前只能达到**文档级平行**，无法实现严格的**句对级平行**

**2. 内容对齐特点**
- 四种语言的文档整体平行度可达到 **99.98%**
- 句子顺序可能存在错乱，但这不影响大语言模型的预训练
- 我们的实验并未对四种语言进行句对级的平行处理，仅在文档级别实现了内容平行

> 💡 **提示**：该数据集主要用于多语言预训练，而非句对级的翻译任务。

## 🤖 模型介绍

### CUTE-Llama

CUTE-Llama 是基于 Llama2-7B 架构开发的多语言模型，我们提供了两个版本：
- **CUTE-Llama-P**：使用平行语料训练的版本
- **CUTE-Llama-NP**：使用非平行语料训练的版本

### 主要特点

- ✨ 扩展了中文、维吾尔语和藏语的词表
- 🎯 针对低资源语言进行了优化
- 🔄 支持跨语言知识迁移

## 📚 引用

如果您使用了我们的数据集或模型，请引用我们的论文：

```bibtex
@inproceedings{zhuang2025cute,
  title={CUTE: A Multilingual Dataset for Enhancing Cross-Lingual Knowledge Transfer in Low-Resource Languages},
  author={Zhuang, Wenhao and Sun, Yuan},
  booktitle={Proceedings of the 31st International Conference on Computational Linguistics},
  pages={10037--10046},
  year={2025}
}
```
