# Contributing to the AD Dataset Catalogue

Thank you for helping make this catalogue more complete! This repository is designed to be a living, community-maintained resource.

## How to Add a Dataset

### Step 1 — Fork the repository

Click **Fork** on GitHub to create your own copy of this repository.

### Step 2 — Edit the data file

Open `data/neuroimaging_genetics.json` and add a new entry at the appropriate position (chronological by `year` is preferred).

Your entry must follow the schema described in [schema.md](./schema.md). Here is a template:

```json
{
  "id": "your-dataset-id",
  "name": "DATASET",
  "full_name": "Full Official Name of the Dataset",
  "year": 2020,
  "data_types": ["MRI", "Genetics", "Clinical"],
  "access": "partial",
  "n_subjects": 500,
  "n_note": "~500",
  "origin": ["USA", "France"],
  "doi": "10.xxxx/xxxxxx",
  "url": "https://dataset-official-url.org",
  "notes": "Brief description of the dataset, its strengths, limitations, and access procedure."
}
```

### Step 3 — Validate your entry

Ensure:
- `id` is unique (not already in the file)
- `doi` is valid and resolves to a peer-reviewed publication
- `data_types` use only values from the controlled vocabulary in schema.md
- `access` is one of: `"open"`, `"partial"`, `"restricted"`

### Step 4 — Open a Pull Request

Submit a PR with:
- A descriptive title: `Add [DATASET NAME] to catalogue`
- A brief justification: why this dataset is relevant to AD research

## What Counts as a Valid Dataset?

A dataset is eligible if it:
1. Is published or documented in a peer-reviewed paper (DOI required)
2. Contains data relevant to Alzheimer's disease or dementia (clinical, neuroimaging, genetic, multi-omics, etc.)
3. Is accessible to researchers (any level of access — open, application-based, or restricted)

## Code of Conduct

Be accurate. Always cite primary sources. Do not add datasets without a verifiable DOI.

## Questions?

Open an Issue on GitHub.
