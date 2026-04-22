
This project explores multimodal learning on clinical imaging data by combining vision–language models and large language models for medical image understanding and captioning.

We work with the `NIH-CXR14-BiomedCLIP` dataset, which contains chest X-ray images, pathology labels, short textual descriptions, and pre-computed image–text embeddings extracted using Microsoft’s BiomedCLIP model.

## Project scope

The goal of this project is to investigate different strategies for leveraging vision–language representations in downstream generative and multimodal tasks, with a focus on:
-	mapping visual embeddings to language models,
-	fine-tuning large multimodal models on domain-specific medical data,

## Repository structure

The repository consists of multiple notebooks: 
- `CLIP_Image_Encoder.ipynb`:
Training a ViT using contrastive learning to obtain a vision encoder. The training is done by using precomputed embeddings obtained from Microsoft’s BiomedCLIP model. More on: [blog post](https://martingkc.github.io/blog/2026/image-captioning-using-clip/)
-	`clip_caption_gpt.ipynb`:
Implements a lightweight MLP that maps BiomedCLIP image embeddings into the input embedding space of a GPT-2 transformer, enabling caption generation directly from CLIP representations. This experiment explores whether language models can be repurposed for medical captioning through embedding-space alignment rather than end-to-end retraining. The notebook also includes an example using a focal loss function to mitigate bias introduced by the dataset’s class imbalance.  More on: [blog post](https://martingkc.github.io/blog/2026/image-captioning-using-clip/)
-	`medgemma_finetune.ipynb`:
Fine-tunes Google’s MedGemma (4B parameters) on chest X-ray images paired with textual descriptions.
The notebook focuses on adapting a large, domain-specific vision–language model to a curated subset of clinical image–caption data and analyzing training stability and qualitative outputs.
-	`QWEN2.5VL_finetune.ipynb`:
Fine-tunes the Qwen2.5-VL model (3B and 7B parameter variants) on a subset of the NIH-CXR14-BiomedCLIP dataset.
This experiment compares different model scales and evaluates how parameter count affects convergence, caption quality, and multimodal alignment on medical imaging data.



## Notes
This repo contains multiple experiments done with the aformentioned dataset, I'd like to put the emphasis on the experiment part. 
Some of the notebooks present on this Repo have blog posts associated to them where I go more in depth on the explanation of the models and of the code. 
