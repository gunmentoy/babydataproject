# Best-Selling Albums Analysis

An exploratory data analysis of the best-selling albums of all time,
covering sales trends, country-level patterns, top artists, and
artists with sustained multi-album success.

**Dataset**: [Kaggle - Best Selling Albums of All Time](https://www.kaggle.com/datasets/ciroduro01/best-selling-albums-of-all-time)  
**Tools**: Python, Pandas, NumPy, Matplotlib, Seaborn, Jupyter Notebook

---

## Key Findings

### 1. Decades Distribution

The **1980s** produced the most best-selling albums, followed closely by the **1970s**. From that peak, the number of best-selling albums has been declining - likely due to shifts in technology, the music industry, and consumer preferences.

![Decades Distribution](analysis%20exports/images/albums_analysis_17_0.png)

### 2. Top Artists by Sales

A small number of artists dominate total sales, demonstrating a **"star power" effect**. The top 5 artists have significantly higher combined sales than the rest, reflecting their cultural impact, talent, and marketing power.

![Top Artists](analysis%20exports/images/albums_analysis_20_0.png)

### 3. Top Countries by Sales

The music industry's success is **geographically concentrated**. The **United States** leads by a wide margin, followed by the **United Kingdom**. These countries are home to major labels, production facilities, and globally influential artists.

![Top Countries](analysis%20exports/images/albums_analysis_23_0.png)

### 4. Artists with Multiple Best-Selling Albums

Repeating best-selling albums is rare - most artists appear only once. The few who have **multiple entries** generate enormous total sales, showing consistent appeal and true staying power.

![Multi-Album Artists](analysis%20exports/images/albums_analysis_26_0.png)

---

## Summary

- The music industry shows strong patterns of **concentration** - in time (1970s–80s), geography (USA & UK), and talent (a select few artists)
- Success is not evenly distributed; it clusters among artists, countries, and decades with the strongest cultural and commercial influence
- Sustained multi-album success is uncommon, making repeat best-sellers truly exceptional

---

## Repository Structure

| File                                    | Description                                        |
| --------------------------------------- | -------------------------------------------------- |
| `script/albums_analysis.ipynb`          | Main analysis: cleaning, visualizations, narrative |
| `script/datasets_join.ipynb`            | Outer join with generated artist awards dataset    |
| `analysis exports/albums_analysis.html` | Exported HTML notebook                             |
| `analysis exports/images/`              | Exported chart images from the analysis            |

---

## How to Run

1. Clone the repo
2. Install dependencies: `pip install pandas numpy matplotlib seaborn jupyter`
3. Open `script/albums_analysis.ipynb` in Jupyter
