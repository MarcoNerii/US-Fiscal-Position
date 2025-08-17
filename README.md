# US Fiscal Data Notebook

This project uses the **Treasury Fiscal Data API** and **FRED API** to explore U.S. fiscal data such as receipts, outlays, deficits, and the Treasury General Account (TGA).

The main analysis is in `main.ipynb`.

---

## Setup

```bash
# (1) Create a virtual environment (optional)
python3 -m venv .venv
source .venv/bin/activate   # on Windows: .venv\Scripts\activate

# (2) Install dependencies
pip install pandas requests matplotlib plotly python-dotenv jupyter
```

---

## Running

```bash
jupyter notebook main.ipynb
```

---

## API Keys

- **Fiscal Data** (Treasury) → does not need a key  
- **FRED (GDP data)** → requires a key from https://fred.stlouisfed.org/

### How to set your FRED key (macOS / Linux)

Add this line to your `~/.zshrc` (or `~/.bashrc`):

```bash
export FRED_API_KEY="your_fred_api_key_here"
```

Reload your shell:

```bash
source ~/.zshrc
```

Check it works:

```bash
echo $FRED_API_KEY
```

In Python:

```python
import os
fred_key = os.getenv("FRED_API_KEY")
```

---

## What you can do

- **Receipts / Outlays by category (stacked charts)**
- **Monthly deficits / surpluses**
- **TGA daily balance**
- **Cumulative flows by fiscal year**
- **Normalize by GDP (% of GDP)**

Charts are available in both **Matplotlib** and **Plotly**.

---

## Notes

- Treasury data (MTS/DTS) is in **millions of USD** → divide by `1000` to plot in **billions**.  
- GDP denominators from FRED helpers are also in **millions**.  
- If you see weirdly large numbers, double-check the units.

---

## License

Data comes from U.S. Treasury Fiscal Data and FRED (St. Louis Fed). Both are public sources. This repo is for research/education.
