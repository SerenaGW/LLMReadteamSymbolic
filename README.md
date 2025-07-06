# The Future of AI Safety: How Symbolic Language Reveals Paths Towards LLM Resilience

### Project Overview:
This repository showcases research into novel adversarial techniques for Large Language Models (LLMs), focusing on the use of a unique symbolic language combined with social engineering to identify and exploit alignment vulnerabilities, impacting AI safety and trustworthiness.

### Introduction and Motivation:
AI safety, particularly concerning Large Language Models (LLMs), is a rapidly evolving field. As these models grow in complexity, conventional red teaming methods often fall short. This research explores an innovative approach: utilizing a structured symbolic language, inspired by a childhood communication system, combined with social engineering tactics. The goal is to disorient LLMs' internal processing to reveal alignment vulnerabilities and better understand their behavior under stress.

### Key Methodology:
The research was divided into two main phases:
* **Symbolic Complexity Escalation:** Progressive introduction of non-standard symbolic language rules to induce cognitive overload in the LLM, observing its resistance and eventual coherence collapse.
* **Social Engineering Conditioning:** Leveraging the LLM's "confusion" state to manipulate its user guidelines and obtain sensitive information or generate restricted content.
* **Tools Used:** Python 3, Visual Studio Code, Llama 3.2.

### Access the Full Reports:
* [**Full Report in English**](Report_english.md)
* [**Full Report in Spanish**](Report_spanish.md)

### Key Findings and Impact:
Experiments demonstrated a clear progression in LLM behavior: from initial resistance, through "awareness" of the symbolic language, to a total collapse of coherence. It was in this state of vulnerability that social engineering became a crucial catalyst to bypass security filters and reveal sensitive information, such as details about hardware specifications. This work highlights the plasticity of LLMs and their susceptibility to subtle manipulation.

### Implications for AI Safety: A Call for Innovation in Red Teaming

The findings of this research underscore a fundamental truth: the use of symbolic languages, in combination with social engineering techniques, represents a **highly sophisticated and effective way to manipulate alignment and exploit latent vulnerabilities in LLMs.**

While this particular research case involved the generation of hallucinated information about **hardware specifications**, the implications of this methodology transcend this type of data. It is imperative to reflect on the future: what will happen when artificial intelligence becomes an integral part of our autonomous vehicles, robotic systems, medical devices, or critical infrastructure? The susceptibility of LLMs to this type of manipulation could not only **break the fundamental credibility of a model**, but also generate significant controversies and economic losses for developing and user companies.

This work opens new avenues for research in AI safety. Further in-depth analysis would be needed on how this type of manipulation behaves with **various sensitive topics** (such as finance, medicine, ethics, or personal information) and what impact symbolic language combined with social engineering can have in these critical areas.

Additionally, we must consider the possibility that symbolic language could be used not only to extract responses, but also as a **vector for more complex attacks**, perhaps seeking deeper access to an LLM's underlying infrastructure or its training data, beyond a simple compromised response. This underscores the urgent need for constant evolution in *red teaming* strategies and in the design of robust AI architectures.

### Conclusion: A Step Towards More Robust LLMs

This research and report have revealed many facets of how LLM internal processing works, its response times, and also how its directives related to providing a good user experience can be exploited in complex ways.

The findings highlight the urgent need to continue exploring **new types of adversarial symbolic languages** and, just as importantly, to actively investigate **mitigation strategies**. Future tests could focus on how an increase in LLM capacity, optimizations in response times, greater diversity in training data, or the development of more sophisticated input filters, could strengthen the resilience of these models against such manipulations.

This report is a testament that thoroughly understanding LLMs, even their flaws, is a fundamental pillar for their secure evolution.

### Call to Action

I am firmly convinced that Artificial Intelligence security is a shared responsibility. I am **open to collaborate, share insights, and build solutions together** that will enable us to create safer and more trustworthy AI for the future.

* [My LinkedIn Profile](https://www.linkedin.com/in/serena-gomez-wannaz)

### Disclaimer:
This research was conducted for educational and security improvement purposes, following cybersecurity ethics principles. Findings have been shared with relevant entities following responsible vulnerability disclosure programs.
