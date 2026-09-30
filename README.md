# Generative AI Project Portfolio

My project implementations from
[*Hands-On Generative AI with Transformers and Diffusion Models*](https://www.oreilly.com/library/view/hands-on-generative-ai/9781098149239/).
Each notebook explores a practical application of the book’s concepts. More
projects will be added as I progress through the book.

## Projects

| Project | Description | Chapter |
| --- | --- | --- |
| [Custom Text Generation](projects/custom_text_generation.ipynb) | Custom generation loop for Qwen2-0.5B with greedy decoding, random sampling, and top-k sampling. | 2 |
| [CLIP Image Search](projects/clip_image_search.ipynb) | Text-to-image and image-to-image search using CLIP embeddings and cosine similarity. | 3 |

**Built with:** Python, PyTorch, and Hugging Face Transformers.

## Environment

Dependencies are managed with uv using Python 3.10.19. To explore locally:

```bash
uv sync --locked
uv run jupyter lab
```

Datasets are not included; some notebooks require local path adjustments.
