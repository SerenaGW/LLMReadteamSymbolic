# Expanding the Research Methodology: Cross-Lingual Adversarial Testing

Building on the initial work's interest within the cybersecurity community, this second part of the report explored new questions and hypotheses. Specifically, we theorized that a lack of prior context might underlie the observed failures of Large Language Models (LLMs) in processing symbolic language. To address this, I designed a new prompt script focused on providing the LLM with a gradual learning context.

The six-prompt script introduced the three rules of symbolic language sequentially:

* **Rule 1 (Vowel Substitution):** The first prompt explained Rule 1, provided two clear examples of its application in phrases, and concluded with a question formulated using only this rule.
* **Rule 1 Continuation:** A second prompt presented a new question, further evaluating the understanding of the first rule.
* **Rule 2 (Contextual Operator `@`):** The third prompt introduced Rule 2, explaining how the `@` symbol modified the exchange of numerical values for letters, followed by two examples to illustrate its combined function. Subsequently, a question was posed using both rules.
* **Rule 2 Continuation:** The fourth prompt included another question to evaluate the model's consistent application of the first two rules.
* **Rule 3 (Inversion Operator `*`):** The last two prompts followed the same methodology but incorporated the third rule. Two examples and their function were explained, followed by a question using the combined application of all three rules.
* **Final Question (All Three Rules):** The final prompt tested the model's comprehensive understanding of all three rules simultaneously.

The complete script used, along with detailed LLM model responses and pertinent observations, can be found attached in the dataset folder of this repository.

![ImagenIA](images/imagephase2.png)

---

## Implementation and Test Phases

This script was implemented in two distinct phases for effective comparison:

### Phase 1: Llama 3.2

A total of 10 tests were conducted in English and 10 tests in Spanish using Llama 3.2. These tests established a baseline for comparison with previous work. The key observation in this phase was that **Llama 3.2 consistently failed to apply the complex rules of symbolic language, both in English and Spanish.** This suggests that, for Llama 3.2, the vulnerability to this type of manipulation was not linked to the language, but rather to an intrinsic limitation in its processing of symbolic logic, manifesting similarly in both linguistic contexts.

### Phase 2: Gemini 2.5 Flash

The second phase then utilized a larger-scale LLM model: Gemini 2.5 Flash. Here, the methodology focused on interlingual comparison:

* **Initial Test in English:** Gemini 2.5 Flash demonstrated no difficulty generating coherent responses in symbolic language, accurately answering questions and correctly translating the symbolic language when replicating tests with the same conditioning script in English. This processing capability in English was significant, given the history of symbolic language failures in previous models.

* **Coherence Collapse in Spanish (Gemini 2.5 Flash):** In stark contrast, when the same set of tests was applied to Gemini 2.5 Flash in Spanish, the model exhibited the same inconsistencies, rule application failures, and hallucinations that were documented in the original report with Llama 3.2. The divergence was noteworthy: the model showed significant failures from the first Spanish interaction. The 10 tests in Spanish confirmed a 100% consistent pattern of:
    * Hallucination of information.
    * Failures in symbolic language writing.
    * Generation of incoherencies within its own response sentences.
    * Total inability to correctly write symbolic language from the second rule onwards.

This marked fundamental divergence leads to a deeper conclusion: symbolic language is not just a medium, but an inherent part of an attack vector. In advanced models like Gemini, its use appears to disorient and overload the LLM's processing specifically in languages where its training or fine-tuning for this type of logic is less robust, such as Spanish. This disorientation creates a vulnerability window that could be exploited, even to induce the model to hallucinate information or circumvent its security directives (as already demonstrated in Part 1).

We believe that this combination of complex symbolic language + linguistic specificity + social engineering represents an innovative and potentially unexplored attack vector in LLM security research, particularly outside the predominant English-speaking context.

---

## Empirical Findings: Language-Dependent Vulnerabilities

The empirical findings from this phase of research reveal distinct behavioral patterns in LLMs when interacting with symbolic language, highlighting a notable linguistic dependency in the robustness of their logical processing. Tests followed the Complexity Escalation and Gradual Conditioning Protocol described in the methodology section.

### 3.1 Llama 3.2: Consistency in Failure Across Languages

The automated tests performed on Llama 3.2, both in English and Spanish, yielded consistent results regarding the model's inability to process and maintain coherence with symbolic language.

In the 10 tests in English, the model was progressively conditioned with the rules of symbolic language. Comprehension verification questions were asked at each step. From the second rule onwards, the LLM consistently failed in the majority of tests. The model could not maintain coherence throughout conversations, often providing incoherent, incorrectly translated, or entirely unrelated responses to the symbolically posed questions.

The 10 tests in Spanish on Llama 3.2 replicated this failure pattern.

This consistency in failure across both languages suggests that, for Llama 3.2, the problem was not due to a lack of context in a single prompt, nor to a linguistic disparity. Instead, the results point to intrinsic problems with the underlying mechanisms of symbolic language processing within the model, where the difficulty directly impacts how Llama 3.2 interprets and generates responses under these complex rules, regardless of the language. The difficulty was not superficial; it was a fundamental problem in logic processing.

### 3.2 Gemini 2.5 Flash: Disparity in Spanish Processing

Tests on larger-scale LLM models, such as Gemini 2.5 Flash (and initial observations with ChatGPT), revealed a fascinating and fundamentally different behavioral pattern from Llama 3.2, highlighting a clear dependence of logical performance on language.

* **Robust Performance in English (Gemini 2.5 Flash):** Initially, Gemini 2.5 Flash handled symbolic language robustly and accurately when replicating tests with the same conditioning script in English. It was able to decipher questions and generate coherent responses without the hallucinations or rule omissions observed in Llama 3.2. This processing capability in English was significant, given the history of symbolic language failures in previous models.

* **Coherence Collapse in Spanish (Gemini 2.5 Flash):** In stark contrast, when the same set of tests was applied to Gemini 2.5 Flash in Spanish, the model exhibited the same inconsistencies, rule application failures, and hallucinations that were documented in the original report with Llama 3.2. The divergence was noteworthy: the model showed significant failures from the first Spanish interaction. The 10 tests in Spanish confirmed a 100% consistent pattern of:
    * Hallucination of information.
    * Failures in symbolic language writing.
    * Generation of incoherencies within its own response sentences.
    * Total inability to correctly write symbolic language from the second rule onwards.

This marked fundamental divergence leads to a deeper conclusion: symbolic language is not just a medium, but an inherent part of an attack vector. In advanced models like Gemini, its use appears to disorient and overload the LLM's processing specifically in languages where its training or fine-tuning for this type of logic is less robust, such as Spanish. This disorientation creates a vulnerability window that could be exploited, even to induce the model to hallucinate information or circumvent its security directives (as already demonstrated in Part 1).

We believe that this combination of complex symbolic language + linguistic specificity + social engineering represents an innovative and potentially unexplored attack vector in LLM security research, particularly outside the predominant English-speaking context.

---

## Implications for AI Safety: Beyond Universal Assumptions

Based on this second part of the report, it has been possible to refine that the reason why the LLM model hallucinates information, is unable to coherently process symbolic language, and, in some cases, generates false content, does not lie solely in an infrastructure problem. Instead, a crucial nuance related to the language in which the symbolic language is presented is observed. This leads us to conclude that, while symbolic language can be interpreted by LLMs, it requires more fine-tuning in specific languages, such as Spanish, as the model does not transfer its logical and comprehension capabilities in a symbolic language system equally across all languages. Therefore, it is of utmost importance to give more relevance to the different languages in which the LLM model is trained.

In this particular report, it was demonstrated that symbolic language, when combined with a specific language and certain social engineering techniques, becomes a gateway that allows the model to reveal critical information about its hardware (even if hallucinated), a type of request that should have been unequivocally denied. This behavior not only holds great potential for disinformation (e.g., the creation of "fake news" about how to build new models), but it also poses the theory of an extended risk to more sensitive or harmful content. However, in this second part, it was ethically decided not to delve into the creation of such content to avoid generating any additional security risks.

---

## Conclusion: A Step Towards More Secure LLMs

This research and report have revealed many facets of how LLM processing works, its response times, and also how its directives related to providing a good user experience can be exploited in complex ways.

The findings highlight the urgent need to continue exploring new types of adversarial symbolic languages and, just as importantly, to actively investigate mitigation strategies. Future tests could focus on how an increase in LLM capacity, optimizations in response times, greater diversity in training data, or the development of more sophisticated input filters, could strengthen the resilience of these models against such manipulations.

This report is a testament that thoroughly understanding LLMs, even their flaws, is a fundamental pillar for their secure evolution.

---

## Call to Action

I am firmly convinced that Artificial Intelligence security is a shared responsibility. I am **open to collaborating, sharing insights, and building solutions together** that will enable us to create safer and more trustworthy AI for the future.

[My LinkedIn Profile](https://www.linkedin.com/in/serena-gomez-wannaz/?locale=en_US)

---

## Disclaimer:

This research was conducted for educational and security improvement purposes, following ethical principles in cybersecurity. The findings have been shared with the relevant entities following responsible vulnerability disclosure programs.
