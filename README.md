# LLM-OASIS

![LLM-Oasis Overview](https://github.com/Babelscape/LLM-Oasis/blob/main/llm-oasis.png)

LLM-Oasis is a comprehensive resource designed for end-to-end factuality evaluation of Large Language Models (LLMs). It provides datasets to support tasks such as claim extraction, claim falsification, and factuality assessment of texts, enabling advancements in factual accuracy for generative AI systems. For more details, refer to the [paper](#).

## Datasets

LLM-Oasis comprises multiple datasets, all hosted on Hugging Face, addressing different stages of the pipeline as described in the paper:

### Claim Extraction

- **[![Hugging Face](https://img.shields.io/badge/Hugging%20Face-Dataset-orange)](https://huggingface.co/Babelscape/LLM-Oasis_claim_extraction) Babelscape/LLM-Oasis_claim_extraction**
  - Contains text-claim pairs used to train the claim extraction system.
  - Refer to Section 3.1 of the paper for more details.

### Claim Falsification

- **[![Hugging Face](https://img.shields.io/badge/Hugging%20Face-Dataset-orange)](https://huggingface.co/Babelscape/LLM-Oasis_claim_falsification) Babelscape/LLM-Oasis_claim_falsification**
  - Includes the outcome of the claim falsification process.
  - Refer to Section 3.2 of the paper for more details.

### Paraphrase Generation

- **[![Hugging Face](https://img.shields.io/badge/Hugging%20Face-Dataset-orange)](https://huggingface.co/Babelscape/LLM-Oasis_paraphrase_generation) Babelscape/LLM-Oasis_paraphrase_generation**
  - Contains factual texts generated from extracted claims.
  - Refer to Section 3.3 of the paper for more details.

### Unfactual Text Generation

- **[![Hugging Face](https://img.shields.io/badge/Hugging%20Face-Dataset-orange)](https://huggingface.co/Babelscape/LLM-Oasis_unfactual_text_generation) Babelscape/LLM-Oasis_unfactual_text_generation**
  - Includes non-factual texts generated from falsified claims and paraphrases.

### Gold Datasets for Manual Annotations

#### Task 1: End-to-End Factuality Evaluation

- **[![Hugging Face](https://img.shields.io/badge/Hugging%20Face-Dataset-orange)](https://huggingface.co/Babelscape/LLM-Oasis_e2e_factuality_evaluation) Babelscape/LLM-Oasis_e2e_factuality_evaluation**
  - Contains data for assessing the factuality of raw texts in natural language.
  - Labels for blind evaluation have been removed.
  - Refer to Section 4.2 of the paper for more details.

#### Task 2: Evidence-Based Claim Verification

- **[![Hugging Face](https://img.shields.io/badge/Hugging%20Face-Dataset-orange)](https://huggingface.co/Babelscape/LLM-Oasis_claim_verification) Babelscape/LLM-Oasis_claim_verification**
  - Contains data for verifying the veracity of a single claim against evidence from Wikipedia.
  - Labels for blind evaluation have been removed.
  - Refer to Section 4.2 of the paper for more details.

## Citation

If you use LLM-Oasis in your work, please cite our paper:

```
@misc{llm-oasis,
  author = {Authors},
  title = {LLM-Oasis: A Resource for End-to-End Factuality Evaluation},
  year = {2024},
  url = {#}
}
