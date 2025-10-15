# microburbs

This repository analyzes Australian residential property transaction data using Python and popular data science libraries. The main workflow is documented in [`microburbs.ipynb`](https://github.com/SacSresta/microburbs/blob/main/microburbs.ipynb).

## Features

- Loads and explores a large Parquet dataset of property transactions.
- Summarizes data types and missing values.
- Renames columns for clarity.
- Provides descriptive statistics for numeric data (e.g. prices, bedrooms, bathrooms, land size).
- Lists unique values for categorical columns (e.g. suburb, property type).
- Prepares data for visualization and further analysis.

## Requirements

The notebook installs and uses:
- `pandas`
- `numpy`
- `matplotlib`
- `seaborn`
- `pyarrow`
- `fastparquet`
- `scikit-learn`

Install dependencies:
```bash
pip install pyarrow fastparquet seaborn scikit-learn pandas matplotlib
```

## Data

The core dataset is a Parquet file containing residential property transaction records with fields like:
- `gid`, `gnaf_pid` (identifiers)
- `listing_source`, `state`, `street`, `suburb`
- `bedrooms`, `bathrooms`, `garage_spaces`
- `building_size`, `land_size`
- `sale_price`, `hedonic_price`
- `property_type`, `market`, `date_sold`, etc.

Example loading code:
```python
df = pd.read_parquet('path/to/transactions.parquet', engine="fastparquet")
```

## Analysis Steps

1. **Setup & Imports:** Installs required packages, imports libraries, and sets up file paths.
2. **Data Loading:** Reads the Parquet file into a DataFrame.
3. **Data Inspection:** Inspects column data types and DataFrame head.
4. **Renaming:** Renames columns for clarity (e.g., `price` → `sale_price`).
5. **Missing Values:** Counts missing entries by column to guide cleaning.
6. **Descriptive Stats:** Summarizes numeric columns (count, mean, std, min, quartiles, max).
7. **Categorical Overview:** Shows unique value counts for key categorical columns.

## Example Output

- DataFrame info and missing values summary.
- Descriptive statistics for numeric columns.
- Unique values for categorical columns.
- Ready to extend for further analysis, modeling, or visualization.

## Usage

Open and run the notebook:

```bash
jupyter notebook microburbs.ipynb
```

Update the Parquet file path to your local copy if needed.

## License

See [LICENSE](LICENSE) for licensing details.

## Acknowledgments

This project uses public Australian property data. See notebook for details on data fields and sources.
