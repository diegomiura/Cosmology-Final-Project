# CMB TT Phase Shift Reconstruction
My final project will explore the neutrino-induced acoustic phase shift as a robust signature of free-streaming radiation. The phase shift is interesting because as shown in Follin 2015 (the same paper referenced in the class notes), it arises under very restrictive conditions. For adiabatic initial conditions, this would mean perturbations that propagate faster than the photon-baryon sound speed. This makes the phase shift a relatively clean probe of beyond-ΛCDM physics and less susceptible to degeneracies that affect things like overall amplitudes. As a focused starting point, I will work from the analysis framework and physical interpretation emphasized in Baumann 2016.

This repository contains my final-project notebook exploring the acoustic phase shift in the CMB temperature power spectrum caused by free-streaming radiation, especially the cosmic neutrino background.

The analysis compares CLASS-generated TT spectra across several `N_eff` values, removes smooth broadband changes, and fits a simple horizontal template shift `Delta ell` to isolate the phase-like residual.

## Contents

- `cmb_tt_phase_shift_reconstruction.ipynb` - main analysis notebook.
- `data/phase_shift_cache/` - cached CLASS spectra used by the notebook.
- `figures/` - generated plots from the analysis.
- `*.pdf` - reference papers used for the project.

## Setup

Create an environment and install the basic Python dependencies:

```bash
python -m venv .venv
source .venv/bin/activate
pip install numpy scipy matplotlib pandas jupyter
```

`classy`/CLASS is optional if the cached spectra are present. If CLASS is unavailable and a cache entry is missing, the notebook falls back to a synthetic toy spectrum for testing only.

## Run

From this folder, start Jupyter:

```bash
jupyter lab cmb_tt_phase_shift_reconstruction.ipynb
```

Run the notebook top to bottom. It will load cached spectra from `data/phase_shift_cache/` and write updated plots to `figures/`.

## Main Result

For the fiducial comparison `N_eff = 4.0` versus `N_eff = 3.046`, the notebook finds a best-fit TT template shift of about `Delta ell = 2.4` after broadband effects are removed. The shift has the expected sign and demonstrates the acoustic phase-shift signature of free-streaming radiation.

## References

- Follin et al. (2015), *First Detection of the Acoustic Oscillation Phase Shift Expected from the Cosmic Neutrino Background*
- Baumann, Green, Meyers, and Wallisch (2017), *Phases of New Physics in the CMB*
