
This project explores multimodal learning on clinical imaging data by combining vision–language models and large language models for medical image understanding and captioning.

We work with the `NIH-CXR14-BiomedCLIP` dataset, which contains chest X-ray images, pathology labels, short textual descriptions, and pre-computed image–text embeddings extracted using Microsoft’s BiomedCLIP model.

## Project scope

The goal of this project is to investigate different strategies for leveraging vision–language representations in downstream generative and multimodal tasks, with a focus on:
-	mapping visual embeddings to language models,
-	fine-tuning large multimodal models on domain-specific medical data,

## Repository structure

The repository consists of the following notebooks:
-	`clip_caption_gpt.ipynb`:
Implements a lightweight MLP that maps BiomedCLIP image embeddings into the input embedding space of a GPT-2 transformer, enabling caption generation directly from CLIP representations. This experiment explores whether language models can be repurposed for medical captioning through embedding-space alignment rather than end-to-end retraining. The notebook also includes an example using a focal loss function to mitigate bias introduced by the dataset’s class imbalance.
-	`medgemma_finetune.ipynb`:
Fine-tunes Google’s MedGemma (4B parameters) on chest X-ray images paired with textual descriptions.
The notebook focuses on adapting a large, domain-specific vision–language model to a curated subset of clinical image–caption data and analyzing training stability and qualitative outputs.
-	`QWEN2.5VL_finetune.ipynb`:
Fine-tunes the Qwen2.5-VL model (3B and 7B parameter variants) on a subset of the NIH-CXR14-BiomedCLIP dataset.
This experiment compares different model scales and evaluates how parameter count affects convergence, caption quality, and multimodal alignment on medical imaging data.



## Notes

This project was developed as part of an academic coursework but is structured as a set of self-contained experiments rather than a single production pipeline. The emphasis is on experimentation, comparison across architectures, and understanding the trade-offs of different multimodal modeling approaches in the medical domain.
