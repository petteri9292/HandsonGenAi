This is repository is for examples/projects from Hands on generative ai book https://www.oreilly.com/library/view/hands-on-generative-ai/9781098149239/.


Chapter 2 goes through the basics of transformer models, their functioning and basic improvements like prompt engineering.
Chapter 3 goes through data compression using neural networks: Autoencoders, VAEs and CLIP.



Project for chapter 2 is implementation of a generate() function that can be used to generate text from a transformer, including sampling and sampling from top results.
Project for chapter 3 is an implementation of image search, both using text and images. It uses CLIP to generate embeddings and finds the closest embedded images.

## Python environment

Install [uv](https://docs.astral.sh/uv/getting-started/installation/), then run
these commands from the repository root:

```bash
uv sync --locked
uv run python --version
```

uv downloads Python **3.10.19** when needed and creates a local `.venv`.
`pyproject.toml` declares the dependencies, `.python-version` selects Python,
and `uv.lock` records the resolved package versions. The system Python
installation is unchanged. Commit all three files when sharing the setup;
`.venv` is ignored by Git.

The main ML libraries stay on the API versions used by these notebooks:
PyTorch 2.6, Transformers 4.56, Diffusers 0.35, and Datasets 3.6. `genaibook`
0.1.1 provides the imported book helpers, including `SampleURL` and
`plot_noise_and_denoise`. Its dependencies also include packages used in later
book chapters.

On Linux and Windows, PyTorch, torchvision, and torchaudio use the official
[CUDA 12.4 wheels](https://pytorch.org/get-started/previous-versions/#v260).
GPU execution needs a compatible NVIDIA driver; the Python dependencies supply
the CUDA runtime libraries. Check GPU access with:

```bash
uv run python -c "import torch; print(torch.__version__); print('CUDA available:', torch.cuda.is_available())"
```

## Running notebooks

In VS Code, open a notebook and use **Select Kernel → Python Environments** to
choose this repository's `.venv/bin/python` (Windows: `.venv\Scripts\python.exe`).
The environment includes `ipykernel` and `ipywidgets`. The saved kernel display
names such as `Handsongenai` and `base` refer to the original author's environments.

Alternatively, start JupyterLab from the repository root:

```bash
uv run jupyter lab
```

Run cells in order. Initial model and dataset loads download files from Hugging
Face; `uv sync` installs packages without downloading those model weights or
datasets. Diffusion and training examples can require substantial GPU memory.

## Existing notebook limitations

The environment setup does not change the notebooks:

- `4ch_Diffusion.ipynb` ends with unfinished preprocessing cells: the dataset
  identifier appears misspelled, `transforms.ReSize` should be `transforms.Resize`,
  and the transform function needs to return the transformed examples.
- `3ch_Datacompression_1.ipynb` uses names that are not imported, including
  `torch`, `get_device`, `F`, `plt`, `tqdm`, and `trange`.
- `projects/3ch_project.ipynb` needs the local image dataset and updates to its
  hardcoded Windows `F:/...` paths. The images and generated embeddings CSV are
  excluded from Git.
- `First_chapter_examples.ipynb` duplicates `1ch_Introduction.ipynb`.
  Prefer `2ch_Transformers.ipynb` over the older `Second_chapter_examples.ipynb`;
  skip the older notebook's `!pip uninstall/install genaibook` cell when using
  this uv-managed environment.



<img width="281" height="400" alt="image" src="https://github.com/user-attachments/assets/cc6d1bc8-2e9e-429d-8358-ab8370ffcb84" />
