<img src="assets/iccs-logo-big.png"  width="355">

<a target="_blank" href="https://colab.research.google.com/github/Cambridge-ICCS/iccs-ss-2026-downscaling-tutorial">
  <img src="https://colab.research.google.com/assets/colab-badge.svg" alt="Open In Colab"/>
</a>

# ICCS Summer School 2026 — Temperature Downscaling with a U-Net

This repository contains the ICCS Summer School 2026 practical on spatial downscaling of ERA5 2-m temperature over Southeast Asia using a U-Net in PyTorch. The notebooks can be run with Google Colab (on a GPU-based runtime) without local installations. Participants are strongly encouraged to use the VS Code plugin for Google Colab.

## Contents

- [Learning Objectives](#learning-objectives)
- [Teaching Material](#teaching-material)
- [Preparation and Prerequisites](#preparation-and-prerequisites)
- [Data](#data)
- [CDS API Key Handling](#cds-api-key-handling)
- [Installation and Setup](#installation-and-setup)
- [License](#license)
- [Contribution Guidelines and Support](#contribution-guidelines-and-support)

## Learning Objectives

By the end of this practical, participants should be able to:
- Explain spatial downscaling and why it matters for climate applications.
- Describe the U-Net architecture for image-to-image regression.
- Prepare geospatial fields for CNN training in PyTorch.
- Train and evaluate a U-Net for 1° to 0.25° temperature downscaling.
- Explore extension ideas beyond the baseline model.

## Teaching Material

### Exercises

- `notebooks/unet_temperature_downscaling_exercise.ipynb`
  - Participant notebook used during the session.
  - Contains guided TODO-style implementation steps.

### Worked Solution

- `notebooks/unet_temperature_downscaling_solution.ipynb`
  - Complete worked solution for debrief and post-session review.

Recommended teaching order:
1. Start with `exercise` notebook.
2. Use `solution` notebook for walkthrough and recap.

### Running on Google Colab

You can run both notebooks directly in Colab from this repository:
- Exercise notebook: `notebooks/unet_temperature_downscaling_exercise.ipynb`
- Solution notebook: `notebooks/unet_temperature_downscaling_solution.ipynb`

The "Open in Colab" badge at the top of this README launches the repository in Colab.

## Preparation and Prerequisites

To get the most out of this practical, participants should have basic familiarity with:

### Mathematics and Machine Learning

- Basic regression concepts.
- Matrix and tensor representations of data.
- High-level neural network concepts (layers, training, validation).

### Python

- Core Python syntax and functions.
- Basic use of `numpy`, `matplotlib`, and Jupyter notebooks.
- Basic PyTorch familiarity is helpful but not required.

### Git and GitHub

- Cloning a repository.
- Committing and pushing changes.

### Pre-Session Requirement (Important)

Participants should download data **before** attending.
CDS downloads can take significant time depending on queue/server load; doing this during the class can consume most of the hands-on session. If you do not have a CDS API key, you can download the pre-procured data using `gdown` from Google Drive (instructions in the notebook).

## Data

The tutorial expects these files in `data/`:

| File | Description |
|---|---|
| `data/gph_se_asia.nc` | Surface geopotential over SE Asia (static field) |
| `data/t2m_2000.nc` | ERA5 2m temperature (2000, 6-hourly, 0.25°) |
| `data/t2m_2001.nc` | ERA5 2m temperature (2001, 6-hourly, 0.25°) |

## CDS API Key Handling

(Ignore if downloading from Google Drive) The notebooks are set up to read a local API key file when `DOWNLOAD_DATA=True`.

- Create a file named `CDS_API_KEY` in the repository root.
- Put your CDS API key on a single line.
- The code writes `~/.cdsapirc` automatically when download is enabled.
- Notebook source keeps `REPLACE_WITH_YOUR_OWN_CDS_API_KEY` as a safe placeholder.

`CDS_API_KEY` is ignored by git via `.gitignore`.

## Installation and Setup

There are two options for participating in this practical:

- via a [Local Install](#local-install)
- on [Google Colab](#google-colab)

We recommend the local install approach if you want to keep a persistent working copy and run reliably without session limits.

### Local Install

#### 1. Clone or fork the repository

Clone via HTTPS:

```bash
git clone https://github.com/Cambridge-ICCS/iccs-ss-2026-downscaling-tutorial.git
cd iccs-ss-2026-downscaling-tutorial
```

If you want to preserve your changes in your own GitHub account, fork first and then clone your fork.

#### 2. Create and activate a virtual environment

The guide below assumes a local unix installation (Linux, macOS). Windows users are instructed to use Windows Subsystem for Linux (WSL).

```bash
python3 -m venv .venv
source .venv/bin/activate
```

#### 3. Install dependencies

```bash
pip install --upgrade pip
pip install -r requirements.txt
```

#### 4. Run Jupyter Notebook

From repository root:

```bash
jupyter notebook
```

Then open one of:
- `notebooks/unet_temperature_downscaling_exercise.ipynb`
- `notebooks/unet_temperature_downscaling_solution.ipynb`

#### 5. (Optional) Register the environment as a notebook kernel

If your notebook server does not detect the environment, run:

```bash
python -m ipykernel install --user --name=downscaling-venv
```

### Google Colab

Use the badge at the top of this README to open the repository in Colab.

Notes:
- Running in Colab requires a Google account.
- Colab sessions are ephemeral, so save your notebook outputs and changes externally.

### License

See `LICENSE`.

## Contribution Guidelines and Support

If you spot an issue with these materials, please open an issue in the repository.

Contributions are welcome. A typical workflow is:
1. Fork the repository.
2. Create a branch with your changes.
3. Open a pull request describing the updates.

For support adapting or delivering this practical, please contact ICCS via GitHub.
