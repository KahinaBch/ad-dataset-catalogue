# Dataset Catalogue Schema

This document defines the schema for all dataset entries in this catalogue.

## File: `data/neuroimaging_genetics.json`

Each entry in the JSON array must conform to the following schema:

| Field | Type | Required | Description |
|-------|------|----------|-------------|
| `id` | string | ✅ | Unique lowercase identifier (e.g., `"adni"`) |
| `name` | string | ✅ | Short dataset name (e.g., `"ADNI"`) |
| `full_name` | string | ✅ | Full official name of the dataset |
| `year` | integer | ✅ | Year of first publication or establishment |
| `data_types` | string[] | ✅ | List from controlled vocabulary (see below) |
| `access` | enum | ✅ | One of: `"open"`, `"partial"`, `"restricted"` |
| `n_subjects` | integer | ✅ | Approximate number of participants (used for sorting) |
| `n_note` | string | ✅ | Human-readable participant count (e.g., `"~2,000+"`) |
| `origin` | string[] | ✅ | Country/countries of participant recruitment |
| `doi` | string | ✅ | DOI of the primary publication (without `https://doi.org/`) |
| `url` | string | ✅ | Official dataset/resource URL |
| `notes` | string | ✅ | Brief scientific notes, limitations, access instructions |

## Controlled Vocabulary — `data_types`

Only use values from this list:
```
MRI, PET, CSF, Blood, Genetics, Proteomics, Metabolomics,
Transcriptomics, Epigenomics, Exposomics, Cognitive, Clinical,
Neuropathology, Lifestyle, EEG, MEG, Eye-tracking, Sleep
```

## Access Levels

| Value | Meaning |
|-------|---------|
| `"open"` | Freely available, no application required (e.g., OASIS, ANMerge) |
| `"partial"` | Application required but generally accessible to researchers |
| `"restricted"` | Requires institutional agreement, ethics, or significant approval process |

## Validation Rules

- `year` must be ≥ 1950 and ≤ current year
- `doi` must not include `https://doi.org/` prefix
- `access` must be exactly one of the three enum values
- `data_types` must only contain items from the controlled vocabulary above
- `origin` must use ISO country names (e.g., `"USA"`, `"UK"`, `"France"`)
