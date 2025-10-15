
<div align="center">

# Truth or Mirage?<br>Towards End-to-End Factuality Evaluation <br> with LLM-Oasis

[![Paper](http://img.shields.io/badge/ArXiv-B31B1B.svg)](https://arxiv.org/abs/2411.19655)
[![License: CC BY-NC-SA 4.0](https://img.shields.io/badge/License-CC%20BY--NC--SA%204.0-lightgrey.svg)](https://creativecommons.org/licenses/by-nc-sa/4.0/)
[![Hugging Face Collection](https://img.shields.io/badge/%F0%9F%A4%97%20Hugging%20Face-FCD21D)](https://huggingface.co/collections/Babelscape/llm-oasis-674db6e4ff329619b8ed6b82)


  <img src="https://github.com/Babelscape/FENICE/blob/master/Sapienza_Babelscape.png?raw=True" height="70">
</div>

![LLM-Oasis Overview](https://github.com/Babelscape/LLM-Oasis/blob/main/llm-oasis.png)

This repository contains the resource introduced in the paper: ["Truth or Mirage? Towards End-to-End Factuality Evaluation with LLM-Oasis"](https://arxiv.org/abs/2411.19655).
**LLM-Oasis** is a large-scale resource for end-to-end factuality evaluation
obtained by extracting and falsifying information from Wikipedia. 
Specifically, given a text from Wikipedia, we extract a set of factual and unfactual claims, with
the latter obtained by falsifying one of the facts expressed in the original text. Starting from
these sets, we design two claims2text tasks and generate a **factual text**, which is a paraphrase
of the original one, and its **unfactual counterpart**, featuring the falsified claim. This resulted in
81k ⟨factual, unfactual⟩ pairs that are suitable for training and evaluating fact-checking systems.

## Datasets

LLM-Oasis comprises multiple datasets, all hosted on Hugging Face, addressing different stages of the pipeline as described in the [paper](https://arxiv.org/abs/2411.19655):

### Claim Extraction

- <img src="https://huggingface.co/front/assets/huggingface_logo.svg" alt="Hugging Face" width="20" height="20"> [Babelscape/LLM-Oasis_claim_extraction](https://huggingface.co/datasets/Babelscape/LLM-Oasis_claim_extraction) 
  - Contains the text-claims pairs used to train the claim extraction system.
  - Refer to Section 3.1 of the paper for more details.

### Claim Falsification

- <img src="https://huggingface.co/front/assets/huggingface_logo.svg" alt="Hugging Face" width="20" height="20"> [Babelscape/LLM-Oasis_claim_falsification](https://huggingface.co/datasets/Babelscape/LLM-Oasis_claim_falsification)
  - Includes the outcome of the claim falsification process.
  - Refer to Section 3.2 of the paper for more details.

### Paraphrase Generation

- <img src="https://huggingface.co/front/assets/huggingface_logo.svg" alt="Hugging Face" width="20" height="20"> [Babelscape/LLM-Oasis_paraphrase_generation](https://huggingface.co/datasets/Babelscape/LLM-Oasis_paraphrase_generation)
  - Contains the factual texts, i.e., the paraphrases, generated from the extracted claims.
  - Refer to Section 3.3 of the paper for more details.

### Unfactual Text Generation

- <img src="https://huggingface.co/front/assets/huggingface_logo.svg" alt="Hugging Face" width="20" height="20"> [Babelscape/LLM-Oasis_unfactual_text_generation](https://huggingface.co/datasets/Babelscape/LLM-Oasis_unfactual_text_generation)
  - Includes the non-factual texts generated from the set of extracted claims, including the falsified one.

## Gold Benchmark

### Task 1: End-to-End Factuality Evaluation

- <img src="https://huggingface.co/front/assets/huggingface_logo.svg" alt="Hugging Face" width="20" height="20"> [Babelscape/LLM-Oasis_e2e_factuality_evaluation](https://huggingface.co/datasets/Babelscape/LLM-Oasis_e2e_factuality_evaluation)
  - Contains data for assessing the factuality of raw texts in natural language.
  - Labels have been removed for blind evaluation.
  - Refer to Section 4.2 of the paper for more details.

#### 🚨 Evaluate your LLM 🚨
Do you want to evaluate your LLM as an end-to-end factuality evaluator on our gold benchmark?
Submit your predictions here: [Submission form](https://docs.google.com/forms/d/111sD6sMXm85F-iSCHhE868-6QlEE6S-xhePJawZ1OPA/)

Upload a .jsonl whose entries are formatted like this:
```
{
  'id': str # matching the 'id' value in Babelscape/LLM-Oasis_e2e_factuality_evaluation;
  'factual': bool # where True indicates that the text is factual, False, conversely.
}
```



### Task 2: Evidence-Based Claim Verification

- <img src="https://huggingface.co/front/assets/huggingface_logo.svg" alt="Hugging Face" width="20" height="20"> [Babelscape/LLM-Oasis_claim_verification](https://huggingface.co/datasets/Babelscape/LLM-Oasis_claim_verification)
  - Contains data for verifying the veracity of a single claim against evidence from Wikipedia.
  - Labels have been removed for blind evaluation.
  - Refer to Section 4.2 of the paper for more details.



## License
This work is under the [Attribution-NonCommercial-ShareAlike 4.0 International (CC BY-NC-SA 4.0) license](https://creativecommons.org/licenses/by-nc-sa/4.0/).


## Citation

If you use LLM-Oasis in your work, please cite our paper:

```
@article{10.1162/COLI.a.575,
    author = {Scirè, Alessandro and Bejgu, Andrei Stefan and Tedeschi, Simone and Ghonim, Karim and Martelli, Federico and Navigli, Roberto},
    title = {Truth or Mirage? Towards End-To-End Factuality Evaluation with LLM-Oasis},
    journal = {Computational Linguistics},
    pages = {1-41},
    year = {2025},
    month = {10},
    abstract = {After the introduction of Large Language Models (LLMs), there have been substantial improvements in the performance of Natural Language Generation (NLG) tasks, including Text Summarization and Machine Translation. However, LLMs still produce outputs containing hallucinations, that is, content not grounded in factual information. Therefore, developing methods to assess the factuality of LLMs has become urgent. Indeed, resources for factuality evaluation have recently emerged. Although challenging, these resources face one or more of the following limitations: i) they are tailored to a specific task or domain; ii) they are limited in size, thereby preventing the training of new factuality evaluators; iii) they are designed for simpler verification tasks, such as claim verification. To address these issues, we introduce LLM-Oasis, to the best of our knowledge the largest resource for training end-to-end factuality evaluators. LLM-Oasis is constructed by extracting claims from Wikipedia, falsifying a subset of these claims, and generating pairs of factual and unfactual texts. We then rely on human annotators to both validate the quality of our dataset and to create a gold standard test set for benchmarking factuality evaluation systems. Our experiments demonstrate that LLM-Oasis presents a significant challenge for state-of-the-art LLMs, with GPT-4o achieving up to 60\% accuracy in our proposed end-to-end factuality evaluation task, highlighting its potential to drive future research in the field.},
    issn = {0891-2017},
    doi = {10.1162/COLI.a.575},
    url = {https://doi.org/10.1162/COLI.a.575},
    eprint = {https://direct.mit.edu/coli/article-pdf/doi/10.1162/COLI.a.575/2557982/coli.a.575.pdf},
}
