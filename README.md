# Questionnaire-based classification of chronic kidney disease in diabetes

One notebook, `diabetic_ckd_questionnaire_evaluation.ipynb`, produces every number, table and figure in the manuscript and its Supporting information from the public dataset.

## Data

The dataset is **not stored in this repository**. The notebook downloads it from Mendeley Data and checks its SHA-256 fingerprint:

- A Dataset on Demographic and Lifestyle Factors for Prognosticating Chronic Kidney Disease Progression in Diabetic Patients, version 2. Mendeley Data. doi:[10.17632/hjkzgbxgv5.2](https://doi.org/10.17632/hjkzgbxgv5.2) (CC BY 4.0)
- SHA-256 of the analysed file: `9cef0eb4cd3279c36f9b4816c6a2ccfd480345ee3a57e2dc5c9f722e92793618`

If the download fails, download the CSV from the DOI above and set `DATA_PATH` in the first code cell.

## How to run

**Google Colab (recommended):** open the notebook in Colab and choose *Runtime → Run all*. Nothing needs editing.
**Locally (Python 3.13):**

```bash
pip install -r requirements.txt
jupyter nbconvert --to notebook --execute diabetic_ckd_questionnaire_evaluation.ipynb
```

A full run takes about 20–35 minutes on two CPU cores. Setting `FAST_MODE = True` in the first code cell gives a 5-minute smoke test with reduced resampling (not the published results).

## Outputs

`paper_outputs/` contains:

| Path | Content |
|---|---|
| `paper_numbers.json` | every number quoted in the manuscript |
| `tables/` | all tables as CSV |
| `figures/` | all figures (TIFF, 300 dpi, and PNG) |
| `protocol.json` | the pre-specified analysis plan (protocol version 1.0) |
| `deviations.json` | departures from the protocol (empty) |
| `run_manifest.json` | software versions, run sizes, random seed, dataset fingerprint, figure checks |
| `submission/` | the same files renamed to the manuscript numbering (`numbering_map.csv` gives the mapping) |

Re-running the notebook with the versions in `requirements.txt` reproduces these files. Numerical results can differ in the last decimal place with other library versions.

## Licence

Code: MIT (see `LICENSE`). The dataset is licensed separately by its authors under CC BY 4.0.

## Citation

See `CITATION.cff`. Please cite the manuscript and the dataset when using this code.
