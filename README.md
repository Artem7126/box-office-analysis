# Behind the Blockbusters: What Really Drives Box Office Success?

This project explores what drives financial success in Hollywood films. Using data on revenue, budgets, genres, directors, runtime, and release timing, I investigate patterns that predict ROI and revenue. The goal is to find what factors studios can actually control to improve profitability.

## Blog Post

You can read the full blog post here:  
[https://hackmd.io/f_UXmPOtQPe3EORNjNVFUg?view](https://hackmd.io/f_UXmPOtQPe3EORNjNVFUg?view)

## Project Structure

```730039650/ ├── blog.ipynb # Jupyter notebook with all code and narrative ├── blog.txt # Contains the 
HackMD blog URL ├── README.md # This file ├── data/ │ ├── Highest Holywood Grossing Movies.csv │ 
├── TheNumbers_budget_data.csv │ └── final_dataset.csv └── .git/ # Git tracking folder
```

## How to Run

1. Clone this repo or unzip the folder.
2. Make sure you have Python 3 installed with the following packages:
   ```bash
   pip install pandas numpy matplotlib seaborn scikit-learn statsmodels econml patsy requests
   ```

## Data Sources

### Hollywood Movie Data (Kaggle)

The primary dataset used was the **Enriched IMDb Movies Dataset** from Kaggle, which contains information on box office revenue, IMDb ratings, genres, runtime, and more for top Hollywood films.

- File used: `data/Highest Holywood Grossing Movies.csv`
- Used for: Revenue, ratings, genre, runtime, and metadata analysis

### API-Enriched Data

A paid API was used to enrich the dataset with additional fields. This included [brief description: e.g., production companies, cast, distributor, or financial indicators].

- File used: `data/final_dataset.csv`
- The API call was made during preprocessing. The final merged dataset is saved to CSV and used directly in the notebook.

### Budget Data (The Numbers)

Production budget information was manually collected for approximately **1,000 movies** from [The Numbers](https://www.the-numbers.com/movie/budgets/all), due to limitations on automated scraping.

- File used: `data/TheNumbers_Budget_Data.csv`
- Collection method: Copied and pasted into Excel, then exported to CSV
- Cleaning steps: Some original headers in the Excel file spanned two rows (merged cells). These were manually flattened into single-row headers.
The datasets were merged by matching film titles. Missing budget values in the Kaggle dataset were filled using values from The Numbers via a dictionary-based map.

### Tools:

- **Python** — for all data analysis and cleaning
- **Jupyter Notebook** — for combining code, outputs, and explanations
- **Git & GitHub** — for version control and tracking project progress
- **HackMD** — to publish and present the final blog post online
- **Excel** — used for preprocessing The Numbers budget data (reformatting headers, saving CSV)

### Methods and Techniques:

- **Data Cleaning and Preprocessing**:
  - Title normalization (lowercasing, trimming whitespace)
  - Merging datasets using fuzzy-matched titles
  - Manual handling of multi-row Excel headers
  - Cleaning monetary strings (`$`, commas, `\xa0`) and converting to numeric format

- **Data Analysis**:
  - ROI (Return on Investment) calculations
  - Grouped summary statistics (e.g., average ROI by genre, runtime buckets)
  - Linear regression to model global revenue
  - Causal forest modeling to estimate the effect of release timing on ROI

- **Visualization**:
  - Comparative bar charts and line overlays (e.g., genre vs ROI)
  - Scatter plots (e.g., IMDb rating vs ROI)
  - Runtime-based performance analysis

 ## Replicability

- The notebook `blog.ipynb` runs end-to-end and reproduces all figures and results used in the blog post.
- No live API access is required. All enriched data is saved locally in `final_dataset.csv`.
- All required datasets are included in the `data/` folder.
- Required Python packages are listed and installable with pip.
