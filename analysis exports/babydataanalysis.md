# BABI 4005 baby project


## Importing libraries, and loading data


### Importing Libraries

- **pandas** - For reading CSV files and manipulating data in tables (DataFrames)
- **numpy** - For numerical operations and mathematical calculations
- **matplotlib.pyplot** - For creating charts and visualizations
- **seaborn** - For making more attractive statistical plots and charts



```python
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
```

### Loading Data

Next, we'll load our dataset from a CSV file. The dataset contains information about best-selling albums including:

- **Album**: The name of the album
- **Artist**: The artist who created the album
- **Year**: What year the album was released
- **Sales_Millions**: How many millions of copies were sold
- **Decade**: Which decade the album was released in
- **Country**: Which country the album originated from
- **Genre**: The music genre of the album



```python
df = pd.read_csv('best_selling_albums.csv')
```

### DataFrame Overview

We'll examine the first few rows, get information about the data types, and check for any missing values.


**First 5 rows**

Looking at the first few albums in our dataset to get a sense of what the data looks like:


```python
df.head()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Album</th>
      <th>Artist</th>
      <th>Year</th>
      <th>Sales_Millions</th>
      <th>Decade</th>
      <th>Country</th>
      <th>Genre</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Thriller</td>
      <td>Michael Jackson</td>
      <td>1982</td>
      <td>70</td>
      <td>1980s</td>
      <td>USA</td>
      <td>Pop</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Back in Black</td>
      <td>AC/DC</td>
      <td>1980</td>
      <td>50</td>
      <td>1980s</td>
      <td>Australia</td>
      <td>Rock</td>
    </tr>
    <tr>
      <th>2</th>
      <td>The Dark Side of the Moon</td>
      <td>Pink Floyd</td>
      <td>1973</td>
      <td>45</td>
      <td>1970s</td>
      <td>UK</td>
      <td>Rock</td>
    </tr>
    <tr>
      <th>3</th>
      <td>The Bodyguard</td>
      <td>Whitney Houston</td>
      <td>1992</td>
      <td>45</td>
      <td>1990s</td>
      <td>USA</td>
      <td>Pop</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Bat Out of Hell</td>
      <td>Meat Loaf</td>
      <td>1977</td>
      <td>43</td>
      <td>1970s</td>
      <td>USA</td>
      <td>Rock</td>
    </tr>
  </tbody>
</table>
</div>



**Data Types and Structure**

Seeing what data types each column contains and check for any missing information:


```python
df.info()
```

    <class 'pandas.core.frame.DataFrame'>
    RangeIndex: 49 entries, 0 to 48
    Data columns (total 7 columns):
     #   Column          Non-Null Count  Dtype 
    ---  ------          --------------  ----- 
     0   Album           49 non-null     object
     1   Artist          49 non-null     object
     2   Year            49 non-null     int64 
     3   Sales_Millions  49 non-null     int64 
     4   Decade          49 non-null     object
     5   Country         49 non-null     object
     6   Genre           49 non-null     object
    dtypes: int64(2), object(5)
    memory usage: 2.8+ KB


**Statistical Summary**

Looking at numerical summaries of our data to understand the ranges and averages:


```python
df.describe(include="all")
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Album</th>
      <th>Artist</th>
      <th>Year</th>
      <th>Sales_Millions</th>
      <th>Decade</th>
      <th>Country</th>
      <th>Genre</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>count</th>
      <td>49</td>
      <td>49</td>
      <td>49.000000</td>
      <td>49.000000</td>
      <td>49</td>
      <td>49</td>
      <td>49</td>
    </tr>
    <tr>
      <th>unique</th>
      <td>49</td>
      <td>38</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>7</td>
      <td>5</td>
      <td>10</td>
    </tr>
    <tr>
      <th>top</th>
      <td>Thriller</td>
      <td>Michael Jackson</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>1980s</td>
      <td>USA</td>
      <td>Pop</td>
    </tr>
    <tr>
      <th>freq</th>
      <td>1</td>
      <td>3</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>13</td>
      <td>30</td>
      <td>21</td>
    </tr>
    <tr>
      <th>mean</th>
      <td>NaN</td>
      <td>NaN</td>
      <td>1988.306122</td>
      <td>30.734694</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>std</th>
      <td>NaN</td>
      <td>NaN</td>
      <td>13.731357</td>
      <td>9.346959</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>min</th>
      <td>NaN</td>
      <td>NaN</td>
      <td>1957.000000</td>
      <td>20.000000</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>25%</th>
      <td>NaN</td>
      <td>NaN</td>
      <td>1977.000000</td>
      <td>24.000000</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>50%</th>
      <td>NaN</td>
      <td>NaN</td>
      <td>1987.000000</td>
      <td>28.000000</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>75%</th>
      <td>NaN</td>
      <td>NaN</td>
      <td>1999.000000</td>
      <td>33.000000</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>max</th>
      <td>NaN</td>
      <td>NaN</td>
      <td>2017.000000</td>
      <td>70.000000</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
  </tbody>
</table>
</div>



**Check for Missing Data**

It's important to see if there are any "NA" (missing) values in our dataset that might affect our analysis:


```python
na_counts = df.isna().sum()
total_na = na_counts.sum()

print(f"NA values per column: \n {na_counts}")
print()
print(f"Total NA values: {total_na}")
```

    NA values per column: 
     Album             0
    Artist            0
    Year              0
    Sales_Millions    0
    Decade            0
    Country           0
    Genre             0
    dtype: int64
    
    Total NA values: 0


---

## Data Analysis

In this section, we'll explore the best-selling albums dataset to answer important questions about music industry trends. We'll look at:

**Key Questions We're Looking Into:**

1. Which decades produced the most best-selling albums?
2. Which artists have dominated the best-selling albums list?
3. Do certain countries produce more successful albums than others?
4. Which artists have multiple best-selling albums, showing sustained success?


### 1. Decades Distribution Analysis

**What We're Looking For:**

The music industry has grown significantly over time. By looking at which decades produced the most best-selling albums, we can understand which era was the most successful for the industry. This helps us answer: Was there a "golden age" of music in terms of album sales?

**Why This Matters:**

- Identifies which time periods had the strongest album sales performance
- Shows whether recent decades are producing more successful albums than older ones

**How the Code Works:**

1. `value_counts()` to count how many albums appear in each decade
2. `sort_index()` to arrange decades in chronological order (1950s, 1960s, etc.)
3. A bar chart to visualize which decades had the most best-selling albums
4. Print the counts so we can see the exact numbers



```python
# Which decade produced the most best-selling albums?

# Group the albums by decade and count how many albums appear in each decade
decade_counts = df['Decade'].value_counts().sort_index()

# Create a simple bar chart to visualize the distribution
plt.figure(figsize=(8,5))
decade_counts.plot(kind='bar', color='lightcoral')
plt.title('Number of Albums by Decade')
plt.xlabel('Decade')
plt.ylabel('Count of Albums')
plt.grid(axis='y', alpha=0.3)
plt.show()

# Print the results
print("Number of Albums in Each Decade:")
print(decade_counts)
```


    
![png](babydataanalysis_files/babydataanalysis_17_0.png)
    


    Number of Albums in Each Decade:
    Decade
    1950s     1
    1960s     2
    1970s    12
    1980s    13
    1990s     9
    2000s     8
    2010s     4
    Name: count, dtype: int64


**Key Findings from Decades Distribution:**

The 1980s produced the most best-selling albums, followed by the 1970s. From the peak, numbers of albums that sell well have been decreasing. Potentially due to a shift in the music industry, technology or consumer preferences.


### 2. Top Artists by Sales

**What We're Looking For:**

Just as decades vary in success, individual artists also have vastly different commercial performance. By examining which artists have accumulated the highest total sales across all their best-selling albums, we can identify the most commercially successful artists of all time.

**Why This Matters:**

- Identifies the biggest music superstars in terms of album sales
- Shows which artists have achieved consistent commercial success
- Reveals dominant artists who have shaped the music industry

**How the Code Works:**

1. `groupby('Artist')` to group all albums by the same artist
2. `.sum()` to add up all their sales together
3. `.sort_values(ascending=False)` to rank them from highest to lowest sales
4. `.head(15)` to show only the top 15 artists
5. Reverse the data with `.iloc[::-1]` so the highest bars appear at the top of the chart
6. Print the top 5 artists to see exact numbers



```python
# Which artist had the most album sales combined?

# Group by Artist and sum up their total sales across all albums
artist_sales = df.groupby('Artist')['Sales_Millions'].sum().sort_values(ascending=False).head(15)

# Create a horizontal bar chart
plt.figure(figsize=(8,5))
artist_sales.iloc[::-1].plot(kind='barh', color='lightcoral') # Reverse using .iloc[::-1] for better readability
plt.title('Top 15 Artists by Total Sales')
plt.xlabel('Total Sales (Millions)')
plt.ylabel('Artist')
plt.grid(axis='x', alpha=0.3)
plt.show()

# Print the top 5 artists
print("Top 5 Artists by Total Sales:")
print(artist_sales.tail())
```


    
![png](babydataanalysis_files/babydataanalysis_20_0.png)
    


    Top 5 Artists by Total Sales:
    Artist
    Meat Loaf        43
    Fleetwood Mac    40
    Shania Twain     40
    Bee Gees         40
    Led Zeppelin     37
    Name: Sales_Millions, dtype: int64


**Key Insights from Top Artists:**

The music industry shows a "star power" effect where a small number of highly popular artists dominate the best-selling albums market, the top 5 artists have significantly higher sales than others. These artists have enough popularity and appeal to generate massive album sales, meaning their cultural imapct was HUGE. This reflects their talent, marketing power, cultural relevance, or maybe, all of the above!


### 3. Top Countries by Sales

**What We're Looking For:**

Albums are produced and sold around the world, but some countries may have stronger music industries or cultural influence than others. By examining which countries are associated with the most best-selling albums, we can identify the geographical centers of music industry success.

**Why This Matters:**

- Reveals which countries dominate the global music market
- Shows the geographic distribution of music industry success
- Identifies which countries have produced the most commercially successful music

**How the Code Works:**

1. `groupby('Country')` to group all albums by their country of origin
2. `.sum()` to add up all sales for each country
3. `.sort_values(ascending=False)` to rank countries by total sales
4. Reverse with `.iloc[::-1]` so largest bars appear at the top
5. Print all the country totals to see exact numbers



```python
# Which country had the most album sales combined?

# Group by Country and sum up their total sales across all albums
country_sales = df.groupby('Country')['Sales_Millions'].sum().sort_values(ascending=False)

# Create a horizontal bar chart to show top countries
plt.figure(figsize=(8,5))
country_sales.iloc[::-1].plot(kind='barh', color='lightcoral') # Reverse using .iloc[::-1] for better readability
plt.title('Top 5 Countries by Total Album Sales')
plt.xlabel('Total Sales (Millions)')
plt.ylabel('Country')
plt.grid(axis='x', alpha=0.3)
plt.show()

# Print the top 5 countries
print("Top 5 Countries by Total Sales:")
print(country_sales)
```


    
![png](babydataanalysis_files/babydataanalysis_23_0.png)
    


    Top 5 Countries by Total Sales:
    Country
    USA          897
    UK           458
    Canada        73
    Australia     50
    Ireland       28
    Name: Sales_Millions, dtype: int64


**Key Insights from Top Countries:**

The music industry's success is geographically concentrated, with USA being at the top, producing far more best-selling albums compared to others. The US is home to major music production facilities, record labels, and talented artists as well as significant cultural and econmic influence on the global music market.


### 4. Artists with Multiple Albums - Consistency in Success

**What We're Looking For:**

Not all successful artists are one-hit wonders. Some artists achieve multiple best-selling albums throughout their careers, showing consistent commercial and critical success. This analysis examines which artists have proven their staying power by appearing multiple times in the best-sellers list.

**Why This Matters:**

- Identifies artists with sustained, long-term success (not just lucky with one album)
- Shows which artists have built lasting careers and loyal fan bases
- Reveals true superstars who can consistently produce commercially successful work

**How the Code Works:**

1. `value_counts()` to count how many best-selling albums each artist has
2. Filter to only keep artists with `> 1` album (artists with multiple entries)
3. `groupby('Artist').sum()` to calculate total sales for these repeat artists
4. `.head(5)` to show only the top 5 artists
5. Reverse with `.iloc[::-1]` for proper chart orientation
6. Print the complete list of all artists with multiple albums



```python
# Are there any artists with multiple albums in the dataset? 

# Count how many albums each artist has
artist_count = df['Artist'].value_counts()

# Filter to only show artists with more than 1 album
multi_album_artists = artist_count[artist_count > 1].sort_values(ascending=False)

# Calculate total sales for artists with multiple albums
multi_album_sales = df[df['Artist'].isin(multi_album_artists.index)].groupby('Artist')['Sales_Millions'].sum().sort_values(ascending=False)

# Create a single chart showing top 5 artists by combined sales
plt.figure(figsize=(8, 5))
multi_album_sales.head(5).iloc[::-1].plot(kind='barh', color='lightcoral') # Reverse using .iloc[::-1] for better readability
plt.title('Top 5 Artists with Multiple Albums - By Combined Sales')
plt.xlabel('Total Sales (Millions)')
plt.ylabel('Artist')
plt.grid(axis='x', alpha=0.3)
plt.show()

# Print all artists with multiple albums
print("All Artists with Multiple Albums:")
print(multi_album_artists)
print(f"\nTotal number of artists with multiple albums: {len(multi_album_artists)}")
```


    
![png](babydataanalysis_files/babydataanalysis_26_0.png)
    


    All Artists with Multiple Albums:
    Artist
    Michael Jackson    3
    The Beatles        3
    Eagles             2
    Taylor Swift       2
    Eminem             2
    Various Artists    2
    Whitney Houston    2
    Pink Floyd         2
    Madonna            2
    Name: count, dtype: int64
    
    Total number of artists with multiple albums: 9


**Key Insights from Multiple Album Artists:**

Fewer artists appear in this list compared to the number of total artists in the dataset. They generate an enormous amount of total sales, showing that they're consistent and not just one hit wonder. Repeating best-selling albums is actually quite rare, making these artists truly exceptional. These artists likely have very strong fan bases, effective marketing, or the ability to evolve their music while maintaining appeal to the mass public.


---

## Summary and Key Takeaways

**What We Learned About the Best-Selling Albums Dataset:**

1. Best-selling albums are concentrated in 1970s and 1980s, suggesting these were the most successful periods in music history. The music industry's success has changed over time based on technological, cultural, and economic factors.

2. A small number of artists dominate the best-sellers list with massive total sales, demonstrating the "star effect" in the music industry.

3. The music industry is geographically concentrated, with the United States and United Kingdom producing the majority of best-selling albums. These countries have the infrastructure, talent, and market conditions to support successful music production.

4. While some artists achieve multiple best-selling albums, this is relatively uncommon. Most artists appear only once in the best-sellers list, making repeat success a mark of true excellence.

**Overall Insights:**

- The music industry shows strong patterns of concentration - both in time (certain decades), geography (certain countries), and talent (certain artists)
- Success in music is not evenly distributed but rather concentrated among a select few who have proven their ability to create commercially appealing work
- The artists and countries that dominate the best-sellers list likely represent the highest-quality production, strongest marketing capabilities, and deepest cultural influence in the music industry

This dataset reveals the structure and dynamics of success in the music industry!

