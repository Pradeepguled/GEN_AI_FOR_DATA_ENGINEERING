# Preface

Hello! I’m **Pradeep Guled**, and these are my notes for the **Oracle Cloud Infrastructure — Generative AI Professional** course.

I wrote them mainly from a **Data Engineer’s view**. That means you will not only learn the course topics but also how GenAI connects with real work like data pipelines, ETL/ELT, and enterprise systems.

If you ever looked at the OCI console and thought, “Where do I start?”, or wondered how to use vector search and chatbots, this guide is for you. I kept it short, simple, and a little fun — because learning is easier when it feels light.

What to expect:

- Notes in **easy language**.
- New terms explained the first time.
- A few jokes here and there.

By the end, you will know the certification topics and also understand **how GenAI fits into a Data Engineer’s daily work**.

— *Pradeep Guled*

---

# Table of Contents

0. Preface
1. Introduction to Large Language Models (LLMs)
2. LLM Architecture — Encoders and Decoders
3. Prompting and Prompt Engineering
4. Issues with Prompting

---

# 1. Introduction to Large Language Models (LLMs)

- **What is an LLM?**A Large Language Model (LLM) is a computer program that can **read, understand, and write** human-like text.
- **How it learns:**The model reads **huge amounts of text** (books, articles, websites, code) and learns patterns in language.
- **Why “large”?**Because it has **many internal settings (parameters)** — often billions — that store what it learned.
- **Core ability:**The model learns to **predict the next word** in a sentence. This simple skill lets it do many things: chat, summarize, translate, write code, and more.
- **Everyday example:**Think of an LLM like a very advanced **autocomplete** on your phone. But instead of just finishing one word, it can write paragraphs, answer questions, and explain things.
- **Why companies use LLMs:**

  - Make chatbots for customer help.
  - Summarize long documents.
  - Search inside documents by meaning, not just words.
  - Build smart assistant tools.

---

# 2. LLM Architecture — Encoders and Decoders

LLMs use the **Transformer** idea. Two main parts to know: **Encoders** and **Decoders**.

## Main idea (one line)

- **Encoder = understands text (turns words into meaning).**
- **Decoder = creates text (turns meaning into next words).**

## Encoder (What it does)

- **Input:** A sentence or text.
- **Output:** A set of **vectors** (numbers) that show the meaning.

**Steps inside an encoder:**

1. **Tokenization** — break text into pieces (tokens).
   - Example: “Playing” → “Play” + “ing”.
2. **Embedding** — turn tokens into number vectors.
3. **Self-attention** — the model checks how tokens relate to each other.
   - Example: In “The cat sat on the mat”, the model links “cat” with “sat”.
4. **Layers** — many layers build a final meaning vector.

**Use cases:** Understanding tasks like classification and finding entities.
**Example models:** BERT, RoBERTa.

## Decoder (What it does)

- **Input:** Previous words (and maybe encoder vectors).
- **Output:** The **next word**, one at a time.

**Steps inside a decoder:**

1. Read the words already generated (e.g., “I love”).
2. Use **self-attention** on its own words and **cross-attention** to encoder vectors if present.
3. Predict the next token (e.g., “apples”).
4. Repeat until the output is done.

**Use cases:** Writing tasks like chat, story writing, code generation.
**Example models:** GPT, LLaMA.

## Encoder–Decoder (Both together)

- **How it works:** Encoder reads input and makes meaning vectors. Decoder uses those vectors to create output.
- **Good for:** Translation, summarization, and many Q&A tasks.
- **Example models:** T5, BART.

## Quick memory help

- **Encoder-only:** Reader (understands).
- **Decoder-only:** Writer (creates).
- **Encoder–Decoder:** Read first, then write (translate).

---
