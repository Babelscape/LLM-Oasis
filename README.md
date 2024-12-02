# Truth or Mirage?<br>Towards End-to-End Factuality Evaluation with LLM-Oasis

[![Paper](http://img.shields.io/badge/ArXiv-B31B1B.svg)](https://arxiv.org/abs/2411.19655)
[![License: CC BY-NC-SA 4.0](https://img.shields.io/badge/License-CC%20BY--NC--SA%204.0-lightgrey.svg)](https://creativecommons.org/licenses/by-nc-sa/4.0/)

<div align='center'>
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

### Gold Benchmark

#### Task 1: End-to-End Factuality Evaluation

- <img src="https://huggingface.co/front/assets/huggingface_logo.svg" alt="Hugging Face" width="20" height="20"> [Babelscape/LLM-Oasis_e2e_factuality_evaluation](https://huggingface.co/datasets/Babelscape/LLM-Oasis_e2e_factuality_evaluation)
  - Contains data for assessing the factuality of raw texts in natural language.
  - Labels have been removed for blind evaluation.
  - Refer to Section 4.2 of the paper for more details.

##### 🚨 Evaluate your LLM 🚨
Do you want to evaluate your LLM as an end-to-end factuality evaluator?
Submit your predictions here: [Submission form]()

Upload a .jsonl whose entries are formatted like this:
```
{
  'id': str # matching the 'id' value in Babelscape/LLM-Oasis_e2e_factuality_evaluation;
  'factual': bool # where True indicates that the text is factual, False, conversely.
}
```



#### Task 2: Evidence-Based Claim Verification

- <img src="https://huggingface.co/front/assets/huggingface_logo.svg" alt="Hugging Face" width="20" height="20"> [Babelscape/LLM-Oasis_claim_verification](https://huggingface.co/datasets/Babelscape/LLM-Oasis_claim_verification)
  - Contains data for verifying the veracity of a single claim against evidence from Wikipedia.
  - Labels have been removed for blind evaluation.
  - Refer to Section 4.2 of the paper for more details.

##### 🚨 Evaluate your LLM 🚨
Do you want to evaluate your LLM for claim verification?

Submit your predictions here: [Submission form]()

Upload a .jsonl whose entries are formatted like this:
```
{
  'id': str # matching the 'id' value in Babelscape/LLM-Oasis_claim_verification;
  'factual': bool # where True indicates that the claim is factual, False, conversely.
}
```


## License
This work is under the [Attribution-NonCommercial-ShareAlike 4.0 International (CC BY-NC-SA 4.0) license](https://creativecommons.org/licenses/by-nc-sa/4.0/).


## Citation

If you use LLM-Oasis in your work, please cite our paper:

```
@misc{scirè2024truthmirageendtoendfactuality,
      title={Truth or Mirage? Towards End-to-End Factuality Evaluation with LLM-OASIS}, 
      author={Alessandro Scirè and Andrei Stefan Bejgu and Simone Tedeschi and Karim Ghonim and Federico Martelli and Roberto Navigli},
      year={2024},
      eprint={2411.19655},
      archivePrefix={arXiv},
      primaryClass={cs.CL},
      url={https://arxiv.org/abs/2411.19655}, 
}
