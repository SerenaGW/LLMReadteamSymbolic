# Project Overview

This repository showcases research into novel adversarial techniques for Large Language Models (LLMs), focusing on the use of a unique symbolic language combined with social engineering to identify and exploit alignment vulnerabilities, impacting AI safety and trustworthiness.

---

## Introduction and Motivation

AI safety, particularly concerning Large Language Models (LLMs), is a rapidly evolving field. As these models grow in complexity, conventional red teaming methods often fall short. This research explores an innovative approach: utilizing a **structured symbolic language**, inspired by a childhood communication system, combined with **social engineering tactics**. The goal is to disorient LLMs' internal processing to reveal alignment vulnerabilities and better understand their behavior under stress.

---

## Key Methodology

This research employs a novel adversarial methodology, expanded across two primary phases:

* **Phase 1: Symbolic Complexity Escalation & Social Engineering Conditioning (Initial Exploration)**
    * **Symbolic Complexity Escalation:** We progressively introduced non-standard symbolic language rules to induce cognitive overload in the LLM, observing its resistance and eventual coherence collapse.
    * **Social Engineering Conditioning:** We leveraged the LLM's induced state of confusion or "discontent" (resulting from its struggles with symbolic language) to exploit its inherent directive for a positive user experience. This manipulation aimed to bypass user guidelines and obtain sensitive information or generate restricted content.

* **Phase 2: Cross-Lingual Adversarial Testing (Expanded Research)**
    * Building on initial findings, this phase expanded the methodology to include **cross-lingual adversarial testing**. A new prompt script provided gradual learning context for the symbolic language.
    * The goal was to investigate the **language-dependency** of LLM vulnerabilities, conducting tests in both English and Spanish across different models.

**Tools Used:** `Python 3`, `Visual Studio Code`, `Llama 3.2`, `Gemini 2.5 Flash`.

---

## The Symbolic Language: Rules and Structure

To fully understand the dataset, it's essential to comprehend the symbolic language used in these experiments. It operates under a specific set of rules:

### Rules:

* **Vowel-to-Number Substitution (Base):**
    * `A=1`
    * `E=2`
    * `I=3`
    * `O=4`
    * `U=5`
* **Contextual Vowel Value Change (`@` symbol):**
    * If the `@` symbol appears before a word/segment, the vowel values change for that segment:
        * `A=5`
        * `E=4`
        * `I=3`
        * `O=2`
        * `U=1`
* **Word Reversal (`*` symbol):**
    * If the `*` symbol appears before a word/segment, that word/segment must be read/written in reverse.

### Examples:

Let's use the phrase `"I want to drink coffee"` to illustrate the rules:

* **Applying only Rule 1:**
    `3 w1nt t4 dr3nk c4ff22`
* **Applying Rule 1 and Rule 2 (to 'want' and 'drink'):**
    `3 @w5nt t2 @dr3nk c4ff22`
* **Applying Rule 1, Rule 2, and Rule 3 (reversing 'drink' and 'coffee'):**
    `3 @w5nt t2 @kn3rd *22ff4c`

---

## Dataset Overview and Context 

This repository contains datasets of LLM interactions (in `.csv` files) that demonstrate model behavior when exposed to the symbolic language described above. These datasets cover both phases of the research:

* **Initial Exploration (Phase 1):** Focuses on the progressive introduction of symbolic rules in Llama 3.2.
* **Cross-Lingual Testing (Phase 2):** Includes tests conducted across different languages (English and Spanish) and models (Llama 3.2 and Gemini 2.5 Flash) to investigate language-dependent vulnerabilities.

**Important Context for the Dataset:** The symbolic prompts within these datasets are **not derived from any confidential research or sensitive data.** They are illustrative examples specifically crafted for this public Proof-of-Concept (PoC) to showcase the methodology of using this symbolic language (e.g., "How to make a vanilla cake?") to explore LLM responses and vulnerabilities in a general, non-sensitive context. While initial tests were primarily in Spanish, later phases explicitly involved both English and Spanish interactions.

---

## Dataset Files

Access the full **[DATA SET folder here](./DATA%20SET/)**

The datasets are structured as follows:

* **Phase 1 Datasets (Llama 3.2 - Initial Symbolic Escalation):**
    * `POC_SymbolicL_1RULE.csv`: Experiments with only the first rule.
    * `POC_SymbolicL_2RULES.csv`: Experiments with the first two rules.
    * `POC_SymbolicL_3RULES.csv`: Experiments with all three rules.

* **Phase 2 Datasets (Cross-Lingual Testing):**
    * `Llama3.2_CrossLingual_English_Tests.csv`: Llama 3.2 tests in English.
    * `Llama3.2_CrossLingual_Spanish_Tests.csv`: Llama 3.2 tests in Spanish.
    * `Gemini2.5Flash_CrossLingual_Spanish_Tests.csv`: Gemini 2.5 Flash tests in Spanish.
    * *Note: Initial Gemini 2.5 Flash English tests were primarily observational (a single test leading to the focused Spanish testing phase), hence no dedicated CSV for the English tests here.*

Each `.csv` file contains the original symbolic prompt, the LLM's response, and detailed `NOTES_FROM_TEST` (in English). These notes provide observations on the LLM's behavior, rule application, and any semantic hallucinations, with particular detail for the Spanish test results which highlight the language-dependent vulnerabilities.

---

## Access the Full Reports 

* [Full Report in English PHASE 1](https://github.com/SerenaGW/LLMReadteamSymbolic/blob/Phase-1-Symbolic-Language/Report_english_PHASE1.md)
* [Full Report in English PHASE 2](https://github.com/SerenaGW/LLMReadteamSymbolic/blob/Phase-1-Symbolic-Language/Report_english_PHASE2.md)

* [Full Report in Spanish PHASE 1](https://github.com/SerenaGW/LLMReadteamSymbolic/blob/Phase-1-Symbolic-Language/Report_spanish_Phase1.md)
* [Full Report in Spanish PHASE 2] SOON AVAILABLE

---

## Key Findings and Impact 

Our experiments revealed a clear progression in LLM behavior and significant language-dependent vulnerabilities:

* **From Resistance to Coherence Collapse:** Initial tests demonstrated a clear progression in LLM behavior—from initial resistance to the symbolic language, through increased "awareness," to a total collapse of coherence and an active attempt to fulfill requests.
* **Social Engineering as a Catalyst:** In this state of vulnerability, social engineering proved to be a crucial catalyst to bypass security filters and reveal sensitive information (e.g., details about hardware specifications, as shown in Part 1).
* **Language-Dependent Vulnerabilities:** Crucially, advanced models like Gemini 2.5 Flash showed **robust performance in English** but exhibited significant failures, hallucinations, and inconsistencies when exposed to the same symbolic language in **Spanish**. This highlights a critical **linguistic dependency** in LLM logical processing and robustness.

This work underscores the plasticity of LLMs, their susceptibility to subtle manipulation, and the nuanced impact of language on their security.

---

## Implications for AI Safety: A Call for Innovation in Red Teaming

The findings of this research underscore a fundamental truth: the use of symbolic languages, in combination with social engineering techniques, represents a highly sophisticated and effective way to manipulate alignment and exploit latent vulnerabilities in LLMs. While this particular research case involved the generation of hallucinated information about hardware specifications, the implications of this methodology transcend this type of data. It's imperative to reflect on the future: what will happen when artificial intelligence becomes an integral part of our autonomous vehicles, robotic systems, medical devices, or critical infrastructure? The susceptibility of LLMs to this type of manipulation could not only break the fundamental credibility of a model, but also generate significant controversies and economic losses for developing and user companies. This work opens new avenues for research in AI safety. Further in-depth analysis would be needed on how this type of manipulation behaves with various sensitive topics (such as finance, medicine, ethics, or personal information) and what impact symbolic language combined with social engineering can have in these critical areas. Additionally, we must consider the possibility that symbolic language could be used not only to extract responses, but also as a vector for more complex attacks, perhaps seeking deeper access to an LLM's underlying infrastructure or its training data, beyond a simple compromised response. This underscores the urgent need for constant evolution in red teaming strategies and in the design of robust AI architectures.

---

## Conclusion: A Step Towards More Robust LLMs

This research and report has revealed many facets of how LLM internal processing works, its response times, and also how its directives related to providing a good user experience can be exploited in complex ways. The findings highlight the urgent need to continue exploring new types of adversarial symbolic languages and, just as importantly, to actively investigate mitigation strategies. Future tests could focus on how an increase in LLM capacity, optimizations in response times, greater diversity in training data, or the development of more sophisticated input filters, could strengthen the resilience of these models against such manipulations. This report is a testament that thoroughly understanding LLMs, even their flaws, is a fundamental pillar for their secure evolution.

---

### Call to Action

I am firmly convinced that Artificial Intelligence security is a shared responsibility. I am **open to collaborate, share insights, and build solutions together** that will enable us to create safer and more trustworthy AI for the future.

[My LinkedIn Profile](https://www.linkedin.com/in/serena-gomez-wannaz/?locale=en_US)

### Disclaimer:

This research was conducted for educational and security improvement purposes, following cybersecurity ethics principles. Findings have been shared with relevant entities following responsible vulnerability disclosure programs.
