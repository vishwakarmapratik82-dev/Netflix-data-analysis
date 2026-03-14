# 🎬 Netflix Data Analysis

Exploratory Data Analysis (EDA) of a Netflix movies dataset — uncovering trends in genres, popularity, ratings, and release patterns using Python, Pandas, and Plotly.

---

## 📊 Dataset At a Glance

| Metric | Value |
|--------|-------|
| Total Records | 9,826 movies |
| Columns | 9 |
| Duplicate Rows | 2 |
| Missing Values | 1 row (Title, Popularity, Vote Average, Genre) |
| Clean Dataset | 9,821 movies |
| Release Year Range | 1902 – 2024 |
| English Content | 77.0% (7,568 movies) |
| Non-English Content | 23.0% (2,258 movies) |
| Average Vote Rating | 6.44 / 10 |
| Average Popularity Score | 40.5 |

---

## 📁 Dataset Columns

| Column | Type | Description |
|--------|------|-------------|
| `Release_Date` | object | Date the movie was released (DD-MM-YYYY) |
| `Title` | object | Movie title |
| `Overview` | object | Short plot summary |
| `Popularity` | float64 | TMDB popularity score |
| `Vote_Count` | int64 | Total number of user votes |
| `Vote_Average` | float64 | Average user rating (0–10) |
| `Original_Language` | object | Language the movie was originally made in |
| `Genre` | object | One or more genres (comma-separated) |
| `Poster_Url` | object | URL to the TMDB movie poster |

---

## 🔍 Analysis Workflow

**Step 1 — Data Loading & Preview**
Load `NetflixData.csv` into a Pandas DataFrame and inspect the first few rows using `df.head()`.

**Step 2 — Dataset Structure**
Check shape, column names, and data types using `df.shape`, `df.columns`, and `df.info()`.

**Step 3 — Statistical Summary**
Use `df.describe()` to understand distributions of Popularity (mean: 40.5, max: 5083.9), Vote Count (mean: 1,393), and Vote Average (mean: 6.44).

**Step 4 — Data Quality Check**
Detect 2 duplicate rows and 1 missing value each in Title, Popularity, Vote Average, and Genre columns.

**Step 5 — Data Cleaning**
Remove all duplicates with `df.drop_duplicates()` and drop null rows with `df.dropna()`. Final clean shape: **9,821 rows × 9 columns**.

**Step 6 — Data Preprocessing**
Convert `Release_Date` to datetime and extract the year. Drop non-analytical columns (`Overview`, `Poster_Url`, `Original_Language`). Explode comma-separated genres so each genre occupies its own row — expanding the dataset to **25,779 rows × 6 columns** for genre-level analysis.

**Step 7 — Exploratory Visualizations**
Four interactive Plotly charts to answer key questions about the data.

---

## 📈 Visualizations & Findings

### 1️⃣ Which genre appears most often?

| Rank | Genre | Count |
|------|-------|-------|
| 1 | Drama | 3,743 |
| 2 | Comedy | 3,030 |
| 3 | Action | 2,683 |
| 4 | Thriller | 2,485 |
| 5 | Adventure | 1,852 |
| 6 | Romance | 1,476 |
| 7 | Horror | 1,469 |

> **Conclusion:** Drama is the dominant genre on Netflix, nearly doubling the count of Adventure films.

---

### 2️⃣ Which movies have the highest popularity?

| Rank | Title | Popularity Score |
|------|-------|-----------------|
| 1 | Spider-Man: No Way Home | 5,083.9 |
| 2 | The Batman | 3,827.7 |
| 3 | No Exit | 2,618.1 |
| 4 | Encanto | 2,402.2 |
| 5 | The King's Man | 1,895.5 |

> **Conclusion:** Franchise movies and recent theatrical releases dominate the top popularity rankings.

---

### 3️⃣ How has movie production changed over time?

- Movies span from **1902 to 2024**, covering over a century of film.
- Releases increased steadily from 2000 onward.
- **2021** had the highest number of movies (711), followed by 2018 (530) and 2017 (509).
- The post-2020 dip reflects incomplete data for more recent years.

> **Conclusion:** Content production exploded in the 2010s, with Netflix significantly expanding its library through modern releases.

---

### 4️⃣ Which genres have the highest average popularity?

- **Adventure** movies have the highest average popularity score among all genres.
- **Action** and **Science Fiction** also rank highly.
- **Documentary** and **History** genres show the lowest average popularity.

> **Conclusion:** Audiences gravitate toward high-energy, escapist genres — Adventure, Action, and Sci-Fi consistently outperform others in engagement.

---

### 5️⃣ What is the distribution of popularity scores?

- Popularity is **heavily right-skewed**.
- The median popularity is just **21.2**, while the mean is **40.5** — pulled up by blockbuster outliers.
- Only a tiny fraction of movies achieve popularity scores above 500.

> **Conclusion:** The vast majority of Netflix movies are low-to-mid popularity. Viral blockbusters are the exception, not the rule.

---

## 🌍 Language Breakdown

| Language | Movies | Share |
|----------|--------|-------|
| English (`en`) | 7,568 | 77.0% |
| Japanese (`ja`) | 645 | 6.6% |
| Spanish (`es`) | 339 | 3.5% |
| French (`fr`) | 292 | 3.0% |
| Korean (`ko`) | 170 | 1.7% |
| Other | 812 | 8.3% |

---

## 💡 Overall Insights

- Drama dominates Netflix's catalog by volume, but Adventure leads in audience engagement.
- Franchise films and recent theatrical releases pull far ahead in popularity.
- Netflix has massively diversified its language offering — nearly 1 in 4 movies is non-English.
- Movie production represented in the dataset grew sharply after 2010, peaking in 2021.
- Most movies stay under a popularity score of 50; only blockbusters break out.

---

## 🛠️ Tech Stack

| Tool | Purpose |
|------|---------|
| Python 3 | Core programming language |
| Pandas | Data loading, cleaning & transformation |
| Plotly Express | Interactive charts & visualizations |
| Google Colab | Development & execution environment |

---

## 🚀 How to Run

1. Clone the repository:
   ```bash
   git clone https://github.com/YOUR_USERNAME/netflix-data-analysis.git
   cd netflix-data-analysis
   ```

2. Install dependencies:
   ```bash
   pip install pandas plotly
   ```

3. Place `NetflixData.csv` in the project folder.

4. Open `Netflix_Data_Analysis.ipynb` in Jupyter Notebook or Google Colab and run all cells.

---

## 📂 Repository Structure

```
netflix-data-analysis/
├── Netflix_Data_Analysis.ipynb   # Main EDA notebook
├── NetflixData.csv               # Raw dataset
└── README.md                     # Project documentation
```

---

## 📌 Dataset Source

Data sourced from [Kaggle — Netflix Movies and TV Shows](https://www.kaggle.com/datasets/shivamb/netflix-shows).
Movie metadata and popularity scores powered by [TMDB](https://www.themoviedb.org/).

---

*Built with Python & Plotly · Exploratory Data Analysis Project*
