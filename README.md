# beta2clocks

Docker container for calculating epigenetic clocks from DNA methylation data using [methylCIPHER](https://github.com/HigginsChenLab/methylCIPHER).

## Quick Start

```bash
docker pull ghcr.io/higginschenlab/beta2clocks:latest
```

## Usage

Place your `_cleaned.RData` file in any local directory, then run:

```bash
docker run --rm \
  -v /path/to/your/data:/home/data:rw \
  ghcr.io/higginschenlab/beta2clocks:latest \
  Rscript pipeline/entrypoint.R --input data/YourDataset_cleaned.RData
```

Remember to set `/path/to/your/data` to the directory containing your file — that's the only thing to change.

Results are saved alongside the input file in the same directory.

## Input Format

An `.RData` file containing:
- A variable starting with `DNAm` — beta matrix (samples as rows, CpGs as columns)
- A variable starting with `pheno` — phenotype data with age and sex columns. Expected column names are `cAGE` and `cFEMALE`.

## Clocks Included

Hannum, Horvath1, Horvath2, PhenoAge, DNAmTL, CausAge, AdaptAge, DamAge, GrimAgeV1, GrimAgeV2, PCClocks, SystemsAge, DunedinPACE, DunedinPoAm38, StochasticClocks, EpiDISH, eFRS, DNAmIC

## Citation

To-do

## License

To-do
