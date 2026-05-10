<img src="assets/iccs-logo-big.png"  width="355">


# ICCS Summer School 2026 — Temperature Downscaling with a U-Net

This repository contains the ICCS Summer School 2026 practical on spatial downscaling of ERA5 2-m temperature over Southeast Asia using a U-Net in PyTorch.

## Learning Objectives

By the end of this practical, participants should be able to:
- Explain spatial downscaling and why it matters for climate applications.
- Describe the U-Net architecture for image-to-image regression.
- Prepare geospatial fields for CNN training in PyTorch.
- Train and evaluate a U-Net for 1° to 0.25° temperature downscaling.
- Explore extension ideas beyond the baseline model.

## Notebooks

- `notebooks/unet_temperature_downscaling_exercise.ipynb`
  - Participant notebook used during the session.
  - Contains guided TODO-style implementation steps.
- `notebooks/unet_temperature_downscaling_solution.ipynb`
  - Complete worked solution for debrief and post-session review.

Recommended teaching order:
1. Start with `exercise` notebook.
2. Use `solution` notebook for walkthrough and recap.

## Pre-Session Requirement (Important)

Participants should download data **before** attending.
CDS downloads can take significant time depending on queue/server load; doing this during the class can consume most of the hands-on session.

## Data

The tutorial expects these files in `data/`:

| File | Description |
|---|---|
| `data/gph_se_asia.nc` | Surface geopotential over SE Asia (static field) |
| `data/t2m_2000.nc` | ERA5 2m temperature (2000, 6-hourly, 0.25°) |
| `data/t2m_2001.nc` | ERA5 2m temperature (2001, 6-hourly, 0.25°) |

## CDS API Key Handling

The notebooks are set up to read a local API key file when `DOWNLOAD_DATA=True`.

- Create a file named `CDS_API_KEY` in the repository root.
- Put your CDS API key on a single line.
- The code writes `~/.cdsapirc` automatically when download is enabled.
- Notebook source keeps `REPLACE_WITH_YOUR_OWN_CDS_API_KEY` as a safe placeholder.

`CDS_API_KEY` is ignored by git via `.gitignore`.

## Environment Setup

```bash
python3 -m venv .venv
source .venv/bin/activate
pip install --upgrade pip
pip install -r requirements.txt
```

## Run

From repository root:

```bash
jupyter notebook
```

Then open one of:
- `notebooks/unet_temperature_downscaling_exercise.ipynb`
- `notebooks/unet_temperature_downscaling_solution.ipynb`

## License

See `LICENSE`.
