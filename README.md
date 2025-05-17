# Custom Byte Pair Encoding (BPE) Text Tokenizer

This repository contains a simple implementation of a **Byte Pair Encoding (BPE) tokenizer** from scratch, designed to handle multilingual text, particularly English and Arabic. It demonstrates how to train a BPE tokenizer on UTF-8 encoded text, encode text into token IDs, and decode token IDs back to text.

---

## Table of Contents

- [Introduction](#introduction)
- [Background](#background)
- [Features](#features)
- [Dataset](#dataset)
- [How It Works](#how-it-works)
- [Usage](#usage)
- [Files](#files)
- [Output](#output)
- [Requirements](#requirements)
- [Installation](#installation)
- [Contributing](#contributing)
- [License](#license)

---

## Introduction

Tokenization is a fundamental step in natural language processing (NLP) that converts text into numerical tokens for machine learning models. This project implements a BPE tokenizer that:

- Works on raw UTF-8 byte sequences.
- Learns frequent byte pairs to build a custom vocabulary beyond the base 256 byte tokens.
- Supports mixed English-Arabic text tokenization.
- Provides encode and decode functions.
- Saves learned merges for reuse.

---

## Background

UTF-8 encoding uses 1 to 4 bytes per character, making direct tokenization challenging for multilingual text. Byte Pair Encoding (BPE) overcomes this by iteratively merging frequent adjacent byte pairs into new tokens, resulting in a compact and expressive vocabulary.

---

## Features

- Load and preprocess bilingual English-Arabic dataset.
- Train BPE merges from text data.
- Encode arbitrary text strings into token IDs.
- Decode token ID sequences back into readable text.
- Save merge rules for future encoding/decoding.

---

## Dataset

The tokenizer is trained on a subset of the `"sentence-transformers/parallel-sentences-jw300"` dataset from Hugging Face, containing parallel English-Arabic sentences.

---

## How It Works

1. **Prepare text data**: Combine English and Arabic sentences.
2. **UTF-8 encode** the text to bytes.
3. **Count frequent adjacent byte pairs**.
4. **Iteratively merge** the most frequent pairs into new tokens.
5. **Build encoding and decoding functions** using the merges.
6. **Test encoding and decoding** on sample text.

---

## Usage

### Run the script

```bash
python text_tokenizer.py
