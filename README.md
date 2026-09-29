# 🧠 Word Sense Disambiguation Using NLTK Lesk

## 📌 Overview

This project demonstrates **Word Sense Disambiguation (WSD)** using the **Lesk algorithm** available in the **NLTK (Natural Language Toolkit)** library.

In Natural Language Processing, a single word can have multiple meanings depending on the context in which it is used. The purpose of Word Sense Disambiguation is to determine the **most appropriate meaning of a word based on its surrounding context**.

The **Lesk algorithm** helps identify the correct meaning by comparing the words in the given context with the definitions and related information available in **WordNet**.

This project is implemented using **Python in a Jupyter Notebook**.

---

## 🎯 Objectives

The main objectives of this project are:

* Understand the concept of Word Sense Disambiguation.
* Learn about the Lesk algorithm.
* Import and use `lesk` from NLTK.
* Use WordNet to obtain different meanings of a word.
* Determine the most appropriate word sense based on context.
* Understand how context helps resolve ambiguity in natural language.

---

## 🧠 What is Word Sense Disambiguation?

**Word Sense Disambiguation (WSD)** is the process of identifying the correct meaning of an ambiguous word based on its context.

For example, consider the word:

> **"bank"**

It can mean:

* A financial institution 🏦
* The land beside a river 🌊

Compare:

```text
I deposited money in the bank.
```

Here, **bank** refers to a financial institution.

Whereas:

```text
We sat on the bank of the river.
```

Here, **bank** refers to the land beside a river.

WSD attempts to determine which meaning is intended.

---

## 🔍 What is the Lesk Algorithm?

The **Lesk algorithm** is a classical approach to Word Sense Disambiguation.

It determines the meaning of an ambiguous word by comparing the **context of the word** with the **dictionary definitions (glosses)** of its possible senses.

The basic idea is:

```text
Ambiguous Word
      ↓
Find Possible Meanings
      ↓
Get WordNet Definitions
      ↓
Compare Context with Definitions
      ↓
Find Maximum Overlap
      ↓
Select Most Appropriate Sense
```

NLTK provides an implementation of the Lesk algorithm through:

```python
from nltk.wsd import lesk
```

---

## 🛠️ Technologies Used

* **Python**
* **Jupyter Notebook**
* **NLTK**
* **WordNet**
* **Lesk Algorithm**

---

## ⚙️ Installation

Install NLTK using pip:

```bash
pip install nltk
```

Import NLTK:

```python
import nltk
```

Download the required WordNet resources:

```python
nltk.download('wordnet')
nltk.download('omw-1.4')
```

Depending on the NLTK version, additional tokenizer resources may also be required.

---

## 🚀 Implementation

First, import the Lesk function:

```python
from nltk.wsd import lesk
```

Then define a sentence containing an ambiguous word:

```python
sentence = "I went to the bank to deposit money."
```

Tokenize the sentence:

```python
from nltk.tokenize import word_tokenize

tokens = word_tokenize(sentence)
```

Apply the Lesk algorithm:

```python
sense = lesk(tokens, 'bank')
```

Display the identified sense:

```python
print(sense)
```

To obtain the definition of the identified sense:

```python
print(sense.definition())
```

---

## 🔬 Example

Consider the following sentence:

```python
sentence = "I went to the bank to deposit money."
```

After tokenization:

```text
['I', 'went', 'to', 'the', 'bank', 'to', 'deposit', 'money', '.']
```

Applying Lesk:

```python
sense = lesk(tokens, 'bank')

print(sense)
print(sense.definition())
```

The algorithm attempts to identify the sense of **"bank"** that best matches the surrounding context.

For this context, the appropriate meaning is related to a **financial institution**.

---

## 📚 Understanding WordNet

**WordNet** is a large lexical database of the English language.

It groups words into sets of synonyms called **synsets**.

For example:

```python
from nltk.corpus import wordnet

synsets = wordnet.synsets('bank')

for synset in synsets:
    print(synset)
    print(synset.definition())
```

A word such as **bank** can have multiple synsets because it has multiple meanings.

The Lesk algorithm uses this information to help select the sense that best matches the given context.

---

## 📊 How Lesk Works

Suppose we have:

```text
"I went to the bank to deposit money."
```

The word **bank** is ambiguous.

The algorithm approximately follows this process:

```text
                 "bank"
                    │
          ┌─────────┴─────────┐
          ▼                   ▼
   Financial Bank        River Bank
          │                   │
          ▼                   ▼
    Compare with          Compare with
      context               context
          │                   │
          └─────────┬─────────┘
                    ▼
             Maximum Overlap
                    │
                    ▼
          Most Relevant Sense
```

Words such as **deposit** and **money** provide contextual clues that favor the financial meaning.

---

## 💡 Applications

Word Sense Disambiguation can be useful in:

* 🔎 Information Retrieval
* 🌐 Machine Translation
* 💬 Chatbots
* 📄 Text Analysis
* 📚 Question Answering
* 🧠 Natural Language Understanding
* 🤖 NLP-based AI applications

---

## 📁 Project Structure

```text
NLTK-Lesk-WSD/
│
├── NLTK_Lesk.ipynb
└── README.md
```

---

## 🎓 Learning Outcomes

Through this project, we learn:

* The concept of Word Sense Disambiguation.
* Why words can have multiple meanings.
* How context helps determine word meaning.
* The basic working principle of the Lesk algorithm.
* How to import and use `lesk` from NLTK.
* How WordNet provides different senses and definitions.
* How classical NLP techniques can solve language ambiguity.

---

## 🔮 Future Scope

This project can be extended by:

* Testing Lesk with multiple ambiguous words.
* Comparing different contexts for the same word.
* Implementing a custom version of the Lesk algorithm.
* Comparing Lesk with modern WSD techniques.
* Using WSD as part of a larger NLP preprocessing pipeline.
* Exploring transformer-based approaches for contextual word meaning.

---

## 👨‍💻 Author

**Lucky**

B.Tech Engineering Student | AI & Generative AI Enthusiast
