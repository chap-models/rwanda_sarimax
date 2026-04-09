# Rwanda sarimax model integrated with chap 

The repository integrates a locally developed Sarimax model into chap.

This model is under development, but it is possible to already run it through chap.


### How to run this model locally through chap

1. Make sure you have chap installed (see the chap documentation)
2. You will will need to have docker installed
3. Clone this repository
4. Assuming you have this repository somewhere on your computer, you can run evaluations using the `chap eval` command.


Example of an evaluation using a dataset from a URL:

```bash
chap eval --model-name ../rwanda_sarimax/ --dataset-csv https://raw.githubusercontent.com/dhis2/climate-health-data/refs/heads/main/lao/chap_LAO_admin1_monthly.csv --output-file eval.nc --plot --run-config.debug --backtest-params.n-splits 2 --run-config.run-directory-type use_existing
```

This will generate an `eval.nc` file with results and an HTML plot from the evaluation. Note that we specify `--run-config.run-directory-type` to be `use_existing`. This means that chap will use the directory for the model as a working directory to put dataset files in. This makes it easier to debug and inspect results. Chap will e.g. put files like training_data.csv, etc in this directory. Skipping this option will mean chap makes a new directory in the run folder for each run.


