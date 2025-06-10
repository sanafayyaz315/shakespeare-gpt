# shakespeare-gpt
A minimal, educational Implementation of a character-level GPT trained on Shakespeare, inspired by Andrej Karpathy’s nanoGPT.

# Shakespeare GPT – A Character-Level Transformer Trained from Scratch

This is my personal implementation of a character-level GPT model, trained to generate Shakespearean text using a decoder-only Transformer architecture. The goal was to **learn and implement** the core ideas behind GPT models, following [Andrej Karpathy's](https://youtu.be/kCc8FmEb1nY?si=bQ_MIzMNKzJ2ZYlr) legendary "Lets Build GPT from scratch" series.

---

## What This Project Does

- Trains a small autoregressive Transformer model on Shakespeare's works
- Learns to predict the **next character** given a context of previous characters
- Generates coherent, Shakespeare-style text character-by-character
- Built entirely from scratch using **PyTorch**, with a focus on understanding the internals

---

## Goals & Motivation

This project was an educational deep dive into:

- **Self-Attention** – Understanding how the model decides "what to focus on"
- **Positional Encoding** – How transformers handle sequence order without recurrence
- **Autoregressive Modeling** – Predicting one character at a time, based only on the past
- **Decoder-only Transformer** – Building a GPT-style architecture from the ground up

---

## How Attention Works

At the heart of Transformers is **self-attention**, which allows the model to weigh different parts of the input sequence dynamically.

### Core Steps:
1. **Inputs** are projected into **Query (Q)**, **Key (K)**, and **Value (V)** vectors.
2. The attention mechanism computes:

$$
\text{Attention}(Q, K, V) = \text{softmax}\left( \frac{QK^T}{\sqrt{d_k}} \right)V
$$



3. **Masked self-attention** ensures each character only attends to the ones before it (causality).
4. **Multi-head attention** enables the model to learn different types of patterns in parallel.

---

## 🏗️ Transformer Architecture (GPT-Style)

This project uses a **decoder-only Transformer**, like GPT:

![](/Annotated-Transformers-Architecture.webp)

