# 🌍 Global Telecom Analytics & Data Structure Engine

An interactive, high-performance analytical engine and **Streamlit** dashboard designed to process, clean, and visualize global telecommunications data (internet adoption rates and mobile cellular subscriptions). 

The platform leverages explicit computer science data structures—specifically **FIFO Queues (`collections.deque`)** for rolling computations and **Monotonic Stacks** for anomaly detection—to inspect time-series trajectories across countries.

---

## 🚀 Key Features

- **Algorithmic Country Name Standardization**: Dynamic text-normalization pipeline that standardizes country names and converts acronyms (e.g., `USA` $\rightarrow$ `United States`, `PRC` $\rightarrow$ `China`, `ROK` $\rightarrow$ `South Korea`) without dictionary overhead.
- **Custom Data Structure Algorithms**:
  - **FIFO Queue Engine (`collections.deque`)**: Calculates $N$-year rolling window averages dynamically in $O(1)$ amortized time per entry with automatic sliding eviction.
  - **Monotonic Stack Anomaly Detector**: Audits yearly adoption series to catch non-monotonic Year-over-Year (YoY) drops or data recording outages.
- **Interactive Geospatial Visualization**: Global choropleth maps displaying country-level internet penetration using Plotly projections.
- **Flexible Data Pipeline Strategy**: Configurable missing data handlers (Time-Series Forward/Backward Fill vs. Row Dropping) and outlier correction.
- **Comparative Ranking & Sorting**: Dual-mode ranking to compare nations by absolute adoption level vs. total percentage point growth gained over time.
- **Audit Workbook Export**: Multi-tab Excel export engine containing cleaned dataset outputs, growth leaderboards, and anomaly audit logs.

---

## 🛠️ Tech Stack & Tools Used

| Tool / Library | Purpose |
| :--- | :--- |
| **[Python 3.9+](https://www.python.org/)** | Core runtime environment |
| **[Streamlit](https://streamlit.io/)** | Web UI framework for interactive controls and metric layouts |
| **[Plotly Express & Graph Objects](https://plotly.com/python/)** | High-performance interactive visualizations (Choropleth map, multi-country line charts, horizontal ranking bar charts) |
| **[Pandas](https://pandas.pydata.org/)** | Data melting, merging, grouping, reshaping, and time-series imputation |
| **[NumPy](https://numpy.org/)** | Numerical array operations, outlier filtering, and matrix handling |
| **[OpenPyXL](https://openpyxl.readthedocs.io/)** | Engine for generating multi-sheet `.xlsx` downloadable audit workbooks |
| **`collections.deque`** | Native Python double-ended queue for bounded sliding window computations |
| **`re` (Regular Expressions)** | String pattern sanitization and regex cleaning |

---

## 🗂️ Project Structure

```text
├── app.py                      # Main Streamlit application and analytics pipeline
├── internet.csv                # Raw internet users dataset (Wide format)
├── mobile.csv                  # Raw mobile subscriptions dataset (Wide format)
├── requirements.txt            # Environment dependencies
└── README.md                  # Project documentation
