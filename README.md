# Truth or Mirage?<br>Towards End-to-End Factuality Evaluation with LLM-OASIS

[![Paper](http://img.shields.io/badge/ArXiv-B31B1B.svg)](https://aclanthology.org/2024.findings-acl.841.pdf)
[![License: CC BY-NC-SA 4.0](https://img.shields.io/badge/License-CC%20BY--NC--SA%204.0-lightgrey.svg)](https://creativecommons.org/licenses/by-nc-sa/4.0/)

<div align='center'>
  <img src="https://github.com/Babelscape/FENICE/blob/master/Sapienza_Babelscape.png?raw=True" height="70">
</div>

![LLM-Oasis Overview](https://github.com/Babelscape/LLM-Oasis/blob/main/llm-oasis.png)

LLM-Oasis is a comprehensive resource designed for end-to-end factuality evaluation of Large Language Models (LLMs). It provides datasets to support tasks such as claim extraction, claim falsification, and factuality assessment of texts, enabling advancements in factual accuracy for generative AI systems. For more details, refer to the [paper](#).

## Datasets

LLM-Oasis comprises multiple datasets, all hosted on Hugging Face, addressing different stages of the pipeline as described in the paper:

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

#### Task 2: Evidence-Based Claim Verification

- <img src="https://huggingface.co/front/assets/huggingface_logo.svg" alt="Hugging Face" width="20" height="20"> [Babelscape/LLM-Oasis_claim_verification](https://huggingface.co/datasets/Babelscape/LLM-Oasis_claim_verification)
  - Contains data for verifying the veracity of a single claim against evidence from Wikipedia.
  - Labels have been removed for blind evaluation.
  - Refer to Section 4.2 of the paper for more details.

## License
This work is under the [Attribution-NonCommercial-ShareAlike 4.0 International (CC BY-NC-SA 4.0) license](https://creativecommons.org/licenses/by-nc-sa/4.0/).


## Citation

If you use LLM-Oasis in your work, please cite our paper:

```
@misc{llm-oasis,
  author = {Authors},
  title = {LLM-Oasis: A Resource for End-to-End Factuality Evaluation},
  year = {2024},
  url = {#}
}
