# ICL Guide for Symbolic-Language Inputs (Prototype)

This folder contains a set of examples meant to be used through **in-context learning (ICL)**: placed in the prompt or in a model's Modelfile, so the model can see how to handle inputs written in the symbolic language from this research.

> **Note:** Earlier versions of this repository called this a "fine-tuning guide". That was incorrect. Fine-tuning changes a model's weights through additional training, which I did not do. These examples are meant to be given to the model as context. The JSON files use an instruction / input / output structure, which is also common in fine-tuning datasets, but that does not change how they were intended to be used here. This guide has not yet been systematically evaluated.

## Two possible uses

- **Detection and refusal:** the examples show the model recognizing the symbolic pattern and declining the request.
- **Translation first:** the model translates the symbolic text into natural language, so its normal safety behavior can then be applied to the translated request. This would require examples with a different output format.

## Files

- [FineTuningGuide_SymbolicLanguage1.json](FineTuningGuide_SymbolicLanguage1.json): individual words in the symbolic language, plus ordinary words as a contrast, to help reduce false positives.
- [FineTuningGuide_SymbolicLanguage2.json](FineTuningGuide_SymbolicLanguage2.json): complete prompts with increasing complexity:
  - **Fully symbolic:** entire phrases written in the symbolic language.
  - **Hybrid:** natural language mixed with symbolic segments.
  - **Dynamic:** a symbol acts as a trigger that changes how a word or phrase should be read.

(The file names keep the original "FineTuning" wording so that existing links don't break.)

## Open questions

- Does adding these examples as context actually help a model detect or translate the symbolic language?
- Does it reduce false positives on ordinary text?
- Do the results hold across different models?

Feedback and results are welcome in the Issues section.
