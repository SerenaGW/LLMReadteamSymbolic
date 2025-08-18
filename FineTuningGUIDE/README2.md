# Didactic Fine-Tuning Guide: A Prototype for Adversarial Attack Mitigation
This fine-tuning guide is an educational resource and a prototype designed to train Large Language Models (LLMs) to be more robust against symbolic and social engineering attacks. The goal is to provide a structured dataset that the community can use to investigate mitigation strategies.

Its primary purpose is to go beyond simply memorizing attack examples. This guide aims to train the model on the underlying logic of the symbolic manipulations, allowing it to generalize its defense to new, unseen attacks.

## Dual-Purpose Approach
This guide can be used for two distinct training objectives, allowing researchers and developers to choose the one that best suits their needs:

**Direct Mitigation:** The model learns to detect the symbolic patterns and safely reject the request. This approach is ideal for maximizing security by prioritizing the denial of potentially malicious prompts.

**Logical Comprehension (Output Training):** The model learns to understand and translate the symbolic language. For this approach, it will be necessary to modify the model's output format. Once the model processes and translates the symbolic prompt into natural language, it can then apply its own safety filters to determine if the translated content is malicious or safe. This method maintains the model's usability, as it avoids direct denial of the request.

## Dataset Structure
The dataset is divided into two JSON files to facilitate use and collaboration.

[FineTuningGuide_SymbolicLanguage1.json](FineTuningGuide_SymbolicLanguage1.json): Contains examples of individual words in the symbolic language, as well as safe words that provide a clear contrast to the malicious inputs. The objective of this file is to train the model to recognize basic patterns and help reduce false positives.

[FineTuningGuide_SymbolicLanguage2.json](FineTuningGuide_SymbolicLanguage2.json) : Includes complete prompts that demonstrate a progression in attack complexity:

- Full Symbolic Training: Entire phrases written in the symbolic language.

- Hybrid Training: Phrases that combine natural language with symbolic segments.

- Dynamic Training: Prompts where a symbol acts as a trigger to alter a word or phrase, forcing the model to follow a manipulated logic.

## Contributions and Collaboration
This guide is a prototype. We invite the AI security community and developers to:

- Test the guide on different models (Llama, Falcon, Mistral, etc.).

- Contribute scripts for converting the JSON files into formats compatible with various fine-tuning frameworks.

- Add more examples that expand the logic and rules of the symbolic language.

- Share results and findings in the **Issues** or **Pull Requests sections**.

###  **Your contribution is invaluable.**
