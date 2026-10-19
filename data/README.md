# S&P 500 input

Place the original input at **`data/SPX.csv`**. The CSV is not bundled.

The available local file has these columns:

```text
Date,Open,High,Low,Close,Adj Close,Volume
```

The notebook uses `Date` and `Close`. Dates must be readable by `as.Date()` (the local file uses `YYYY-MM-DD`), and closing prices must be positive numeric values for the log transformation.

The local file spans **December 30, 1927–November 4, 2020**. Filtering to dates on or after January 1, 2000 produces **5,245 prices and 5,244 log returns**, matching the report's counts. The report's plot labels and discussion mention 2024, but the local data does not extend to that year.

The code sorts dates and applies only the lower cutoff; using a file with later observations changes the fitted sample. Keep the exact input and row values when reproducing the archived results. The local project does not document a verified download URL for this particular CSV export.
