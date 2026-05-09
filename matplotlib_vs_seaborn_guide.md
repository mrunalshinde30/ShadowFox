# 📊 Python Data Visualization Guide: Matplotlib vs Seaborn
### A Beginner-Friendly Comparison for Data Science Enthusiasts
**ShadowFox Data Science Internship — Documentation Task**

---

> **Author:** ShadowFox Intern  
> **Topic:** Python Visualization Libraries Comparison  
> **Libraries Covered:** Matplotlib & Seaborn  
> **Level:** Beginner-Friendly  
> **Format:** Jupyter Notebook Compatible

---

## 📋 Table of Contents

1. [Introduction](#1-introduction)
   - 1.1 [What is Data Visualization?](#11-what-is-data-visualization)
   - 1.2 [Why is Visualization Important in Data Science?](#12-why-is-visualization-important-in-data-science)
2. [Library Overview](#2-library-overview)
   - 2.1 [Matplotlib](#21-matplotlib)
   - 2.2 [Seaborn](#22-seaborn)
3. [Graph Types with Code Examples](#3-graph-types-with-code-examples)
   - 3.1 [Line Plot](#31-line-plot)
   - 3.2 [Bar Chart](#32-bar-chart)
   - 3.3 [Scatter Plot](#33-scatter-plot)
   - 3.4 [Histogram](#34-histogram)
   - 3.5 [Pie Chart](#35-pie-chart)
4. [Matplotlib vs Seaborn: Head-to-Head Comparison](#4-matplotlib-vs-seaborn-head-to-head-comparison)
5. [Conclusion](#5-conclusion)
6. [Steps to Run the Project](#6-steps-to-run-the-project)
7. [How to Upload to GitHub](#7-how-to-upload-to-github)
8. [Suggested Screenshots for Submission](#8-suggested-screenshots-for-submission)

---

## 1. Introduction

### 1.1 What is Data Visualization?

Imagine you have a list of 1,000 numbers representing the daily temperatures of a city over the past three years. Reading all those numbers one by one would be overwhelming — and you'd probably miss important patterns!

**Data visualization** is the practice of representing data graphically — using charts, graphs, and plots — so that humans can **see** patterns, trends, and insights quickly and intuitively.

Instead of staring at rows of numbers in a spreadsheet, visualization allows you to:

- **See trends** (e.g., sales are going up every month)
- **Spot outliers** (e.g., one employee sold 10x more than everyone else)
- **Compare groups** (e.g., which city has the highest pollution?)
- **Communicate findings** clearly to others, even non-technical people

> 🧠 **Think of it this way:** A picture is worth a thousand words — and in data science, a good chart is worth a thousand rows of data.

---

### 1.2 Why is Visualization Important in Data Science?

Data science involves collecting, cleaning, analyzing, and drawing conclusions from data. Visualization plays a key role at **every stage** of this process:

| Stage | How Visualization Helps |
|-------|--------------------------|
| **Exploration** | Understand what your data looks like before analyzing |
| **Analysis** | Find correlations, patterns, or anomalies |
| **Communication** | Present your findings to managers, clients, or the public |
| **Model Evaluation** | Plot predictions vs. actual values to assess model performance |

**Real-world examples:**

- 🏥 **Healthcare:** Plotting hospital patient data to spot disease outbreaks
- 📈 **Finance:** Visualizing stock prices over time to detect trends
- 🛒 **E-commerce:** Bar charts showing which products sell the most
- 🌤️ **Weather:** Line plots tracking temperature changes across seasons

In Python, the two most popular libraries for creating visualizations are **Matplotlib** and **Seaborn**. This guide will teach you both!

---

## 2. Library Overview

### 2.1 Matplotlib

#### 📌 Introduction

**Matplotlib** is Python's original and most widely used data visualization library. It was created by **John D. Hunter** in 2003, inspired by MATLAB's plotting capabilities. Think of it as the **"foundation"** of Python visualization — almost every other visualization library (including Seaborn) is built on top of it.

#### ✨ Key Features

- Produces **publication-quality** figures in various formats (PNG, PDF, SVG, etc.)
- Offers **complete control** over every element of a plot (colors, fonts, axes, labels, etc.)
- Works with **any Python data structure** — lists, NumPy arrays, Pandas DataFrames
- Supports **interactive plots** in Jupyter Notebooks
- Can create **complex multi-panel figures** (subplots)
- Has a large community and thousands of **tutorials and examples** online

#### ✅ Advantages

1. **Maximum flexibility** — You can customize literally everything
2. **Widely supported** — Works in scripts, notebooks, web apps, and GUIs
3. **Well-documented** — Extensive official documentation and community resources
4. **Stable and mature** — Over 20 years of active development
5. **Foundation knowledge** — Learning Matplotlib helps you understand all other libraries

#### 🛠️ Common Use Cases

- Creating simple line, bar, scatter, and pie charts
- Building **custom dashboards** with fine-tuned layouts
- **Academic and scientific** publications requiring precise formatting
- Embedding plots in web applications or PDF reports
- Creating **animated visualizations**

---

### 2.2 Seaborn

#### 📌 Introduction

**Seaborn** is a high-level data visualization library built **on top of Matplotlib**. It was created by **Michael Waskom** and released in 2012. Think of Seaborn as Matplotlib's "smart younger sibling" — it makes beautiful, statistically-rich plots with much less code.

Seaborn is especially popular in **data science and machine learning** because it integrates seamlessly with **Pandas DataFrames** and includes built-in statistical tools.

#### ✨ Key Features

- Beautiful **default themes and color palettes** that look professional out of the box
- Built-in support for **statistical visualization** (distribution plots, regression plots, etc.)
- Works directly with **Pandas DataFrames** — just pass column names as strings
- **Automatically handles** grouping, aggregation, and statistical calculations
- Includes specialized plots like **heatmaps**, **violin plots**, and **pair plots**
- Supports **FacetGrid** for creating multi-panel plots easily

#### ✅ Advantages

1. **Much less code** — Beautiful plots in just 1–2 lines
2. **Prettier by default** — No need to spend time on styling
3. **Statistical features built-in** — Adds confidence intervals, regression lines automatically
4. **DataFrame-friendly** — Pass column names directly instead of raw arrays
5. **Great for EDA** — Exploratory Data Analysis becomes much faster

#### 🛠️ Common Use Cases

- **Exploratory Data Analysis (EDA)** — quickly understanding your dataset
- **Statistical visualization** — showing distributions, correlations, and relationships
- Creating **heatmaps** for correlation matrices
- **Machine learning** — visualizing feature relationships and model outputs
- Data science **presentations and reports**

---

## 3. Graph Types with Code Examples

> 💡 **Setup:** Run this cell first in your Jupyter Notebook before any examples below.

```python
# ============================================================
# SETUP CELL — Run this first!
# ============================================================
import matplotlib.pyplot as plt
import seaborn as sns
import numpy as np
import pandas as pd

# Set a consistent style for all plots
plt.rcParams['figure.figsize'] = (8, 5)
print("✅ Libraries imported successfully!")
print(f"Matplotlib version: {plt.matplotlib.__version__}")
print(f"Seaborn version: {sns.__version__}")
```

---

### 3.1 Line Plot

#### 📖 Explanation

A **line plot** (also called a line chart) displays data points connected by a continuous line. It is the best chart type for showing **how something changes over time** or across a continuous sequence.

#### 🎯 Use Case

- Tracking temperature changes over months
- Plotting a company's revenue over years
- Showing a student's test scores across semesters

---

#### 🐍 Matplotlib — Line Plot

```python
# ============================================================
# MATPLOTLIB LINE PLOT
# Tracking average monthly temperature in a city
# ============================================================

# Data: average temperature (°C) for each month
months = ['Jan', 'Feb', 'Mar', 'Apr', 'May', 'Jun',
          'Jul', 'Aug', 'Sep', 'Oct', 'Nov', 'Dec']
temperature = [15, 17, 21, 26, 31, 35, 34, 33, 29, 24, 19, 16]

# Create the figure and axes
plt.figure(figsize=(10, 5))

# Plot the line with markers at each data point
plt.plot(months, temperature,
         color='royalblue',      # Line color
         linewidth=2,            # Line thickness
         marker='o',             # Circle marker at each point
         markersize=8,           # Size of the marker
         markerfacecolor='red',  # Fill color of markers
         label='Temperature (°C)')

# Add titles and labels
plt.title('Average Monthly Temperature — City Weather Data', fontsize=15, fontweight='bold')
plt.xlabel('Month', fontsize=12)
plt.ylabel('Temperature (°C)', fontsize=12)

# Add a horizontal line at 0°C for reference
plt.axhline(y=25, color='orange', linestyle='--', alpha=0.7, label='25°C Reference Line')

# Add a legend
plt.legend(fontsize=11)

# Add a grid for easier reading
plt.grid(True, alpha=0.3)

# Display the plot
plt.tight_layout()
plt.show()
```

**📊 Expected Output:**  
A line chart with 12 data points (one per month) connected by a blue line. Red circle markers highlight each data point. An orange dashed line at 25°C serves as a reference. The chart clearly shows temperature peaking in summer (June) and dipping in winter (January).

---

#### 🐍 Seaborn — Line Plot

```python
# ============================================================
# SEABORN LINE PLOT
# Same temperature data — notice how much cleaner the code is!
# ============================================================

# Create a Pandas DataFrame (Seaborn works best with DataFrames)
df_temp = pd.DataFrame({
    'Month': ['Jan', 'Feb', 'Mar', 'Apr', 'May', 'Jun',
              'Jul', 'Aug', 'Sep', 'Oct', 'Nov', 'Dec'],
    'Temperature': [15, 17, 21, 26, 31, 35, 34, 33, 29, 24, 19, 16]
})

# Create the plot
plt.figure(figsize=(10, 5))

# Seaborn lineplot — just specify x and y column names!
sns.lineplot(data=df_temp,
             x='Month',
             y='Temperature',
             marker='o',
             color='steelblue',
             linewidth=2.5,
             markersize=9,
             label='Temperature (°C)')

# Add a reference line
plt.axhline(y=25, color='coral', linestyle='--', alpha=0.8, label='25°C Reference')

# Titles and labels
plt.title('Average Monthly Temperature — Seaborn Style', fontsize=15, fontweight='bold')
plt.xlabel('Month', fontsize=12)
plt.ylabel('Temperature (°C)', fontsize=12)
plt.legend(fontsize=11)
plt.grid(True, alpha=0.3)

plt.tight_layout()
plt.show()
```

**📊 Expected Output:**  
Very similar to the Matplotlib version, but with Seaborn's cleaner default styling. Notice we passed column names (`'Month'`, `'Temperature'`) as strings instead of raw arrays — this is one of Seaborn's biggest conveniences.

---

### 3.2 Bar Chart

#### 📖 Explanation

A **bar chart** uses rectangular bars to compare values across **different categories**. The height (or length) of each bar represents the value for that category. Bar charts are one of the most commonly used chart types because they're easy to understand at a glance.

#### 🎯 Use Case

- Comparing sales across different products
- Showing population of different cities
- Displaying scores of students in a class

---

#### 🐍 Matplotlib — Bar Chart

```python
# ============================================================
# MATPLOTLIB BAR CHART
# Comparing monthly sales of a small bookstore
# ============================================================

# Data: books sold per month (first 6 months)
months = ['January', 'February', 'March', 'April', 'May', 'June']
books_sold = [120, 95, 140, 180, 160, 200]

# Define colors for each bar (optional — makes it more visually appealing)
colors = ['#FF6B6B', '#4ECDC4', '#45B7D1', '#96CEB4', '#FFEAA7', '#DDA0DD']

# Create the figure
plt.figure(figsize=(10, 6))

# Create the bar chart
bars = plt.bar(months, books_sold, color=colors, edgecolor='black', linewidth=0.8)

# Add value labels ON TOP of each bar
for bar, value in zip(bars, books_sold):
    plt.text(
        bar.get_x() + bar.get_width() / 2,  # x position (center of bar)
        bar.get_height() + 3,                 # y position (just above the bar)
        str(value),                           # Text to display
        ha='center',                          # Horizontal alignment
        va='bottom',                          # Vertical alignment
        fontsize=11,
        fontweight='bold'
    )

# Titles and labels
plt.title('Monthly Book Sales — First Half of 2024', fontsize=15, fontweight='bold')
plt.xlabel('Month', fontsize=12)
plt.ylabel('Number of Books Sold', fontsize=12)
plt.ylim(0, 230)  # Set y-axis limit so labels don't get cut off
plt.grid(axis='y', alpha=0.3)  # Only horizontal grid lines

plt.tight_layout()
plt.show()
```

**📊 Expected Output:**  
A colorful bar chart with 6 bars, one per month. Each bar has its exact sales value displayed above it. The y-axis shows the number of books sold. June has the tallest bar (200 books), and February has the shortest (95 books).

---

#### 🐍 Seaborn — Bar Chart

```python
# ============================================================
# SEABORN BAR CHART
# Same bookstore data — Seaborn automatically adds error bars!
# ============================================================

# Create DataFrame
df_sales = pd.DataFrame({
    'Month': ['January', 'February', 'March', 'April', 'May', 'June'],
    'Books_Sold': [120, 95, 140, 180, 160, 200]
})

plt.figure(figsize=(10, 6))

# Seaborn barplot — notice it uses column names as strings
# 'palette' gives us a beautiful built-in color scheme
sns.barplot(data=df_sales,
            x='Month',
            y='Books_Sold',
            palette='Set2',          # Built-in color palette
            edgecolor='black',
            linewidth=0.8)

# Titles and labels
plt.title('Monthly Book Sales — Seaborn Style', fontsize=15, fontweight='bold')
plt.xlabel('Month', fontsize=12)
plt.ylabel('Number of Books Sold', fontsize=12)
plt.grid(axis='y', alpha=0.3)

plt.tight_layout()
plt.show()
```

**📊 Expected Output:**  
A bar chart with Seaborn's attractive `Set2` color palette. Seaborn automatically applies a polished look without any extra code. The chart is cleaner and requires roughly half the code compared to the Matplotlib version.

---

### 3.3 Scatter Plot

#### 📖 Explanation

A **scatter plot** displays individual data points as dots on a two-dimensional grid. It is used to show the **relationship (correlation) between two numerical variables**. If the dots form a pattern (going up, going down, or clustered), that reveals important insights about how the variables relate to each other.

#### 🎯 Use Case

- Analyzing if study hours correlate with exam scores
- Checking if house size correlates with price
- Exploring if a patient's age correlates with blood pressure

---

#### 🐍 Matplotlib — Scatter Plot

```python
# ============================================================
# MATPLOTLIB SCATTER PLOT
# Relationship between study hours and exam scores
# ============================================================

# Generate sample data using NumPy (reproducible with random seed)
np.random.seed(42)  # This ensures we always get the same "random" data

study_hours = np.random.uniform(1, 10, 50)     # 50 students, 1-10 hours of study
exam_scores = study_hours * 7 + np.random.normal(0, 8, 50)  # Score with some noise
exam_scores = np.clip(exam_scores, 20, 100)    # Scores between 20 and 100

# Create the figure
plt.figure(figsize=(9, 6))

# Scatter plot — each dot is one student
scatter = plt.scatter(study_hours, exam_scores,
                      c=exam_scores,            # Color dots by score value
                      cmap='RdYlGn',            # Red=Low, Yellow=Mid, Green=High
                      s=80,                     # Dot size
                      edgecolors='black',       # Dot border
                      linewidths=0.5,
                      alpha=0.85)               # Slight transparency

# Add a colorbar to explain the color coding
plt.colorbar(scatter, label='Exam Score')

# Add a trend line (linear regression line)
z = np.polyfit(study_hours, exam_scores, 1)    # Fit a line
p = np.poly1d(z)
x_line = np.linspace(1, 10, 100)
plt.plot(x_line, p(x_line), 'r--', linewidth=2, label='Trend Line')

# Titles and labels
plt.title('Study Hours vs Exam Scores (50 Students)', fontsize=15, fontweight='bold')
plt.xlabel('Hours Studied per Day', fontsize=12)
plt.ylabel('Exam Score (out of 100)', fontsize=12)
plt.legend(fontsize=11)
plt.grid(True, alpha=0.3)

plt.tight_layout()
plt.show()
```

**📊 Expected Output:**  
A scatter plot where each dot represents one student. Dots are color-coded from red (low score) to green (high score). A red dashed trend line shows that more study hours generally lead to higher exam scores. This positive correlation is clearly visible.

---

#### 🐍 Seaborn — Scatter Plot

```python
# ============================================================
# SEABORN SCATTER PLOT (with regression line built-in!)
# Same study hours vs exam scores data
# ============================================================

# Create DataFrame
df_students = pd.DataFrame({
    'Study_Hours': study_hours,
    'Exam_Score': exam_scores
})

plt.figure(figsize=(9, 6))

# regplot automatically adds a regression line AND confidence interval shading!
sns.regplot(data=df_students,
            x='Study_Hours',
            y='Exam_Score',
            scatter_kws={
                'color': 'steelblue',
                'edgecolors': 'black',
                's': 80,
                'alpha': 0.8
            },
            line_kws={
                'color': 'red',
                'linewidth': 2,
                'linestyle': '--'
            })

plt.title('Study Hours vs Exam Scores — Seaborn with Regression', fontsize=15, fontweight='bold')
plt.xlabel('Hours Studied per Day', fontsize=12)
plt.ylabel('Exam Score (out of 100)', fontsize=12)
plt.grid(True, alpha=0.3)

plt.tight_layout()
plt.show()
```

**📊 Expected Output:**  
A scatter plot with a regression line AND a shaded confidence interval band around it — all automatically added by Seaborn's `regplot`. This shows not just the trend, but also how confident we are in it. The shaded area gets wider at the edges, indicating less certainty there.

---

### 3.4 Histogram

#### 📖 Explanation

A **histogram** shows the **distribution** of a single numerical variable by grouping values into "bins" (ranges) and showing how many values fall into each bin. Unlike a bar chart (which compares categories), a histogram reveals the **shape of your data** — is it spread out? Concentrated in the middle? Skewed to one side?

#### 🎯 Use Case

- Seeing if student heights follow a normal (bell curve) distribution
- Checking if most customers make purchases under ₹500 or over ₹500
- Understanding whether most movies are between 90–120 minutes long

---

#### 🐍 Matplotlib — Histogram

```python
# ============================================================
# MATPLOTLIB HISTOGRAM
# Distribution of student heights in a school
# ============================================================

# Generate realistic height data (normally distributed)
np.random.seed(0)
heights = np.random.normal(loc=165, scale=10, size=200)  # Mean=165cm, Std=10cm

plt.figure(figsize=(10, 6))

# Create histogram
n, bins, patches = plt.hist(heights,
                             bins=20,           # Number of bins
                             color='steelblue',
                             edgecolor='white',
                             linewidth=0.8,
                             alpha=0.85)

# Color the bins based on height (short=blue, medium=green, tall=red)
bin_centers = 0.5 * (bins[:-1] + bins[1:])
for patch, center in zip(patches, bin_centers):
    if center < 155:
        patch.set_facecolor('#FF6B6B')     # Red for short
    elif center < 175:
        patch.set_facecolor('#4ECDC4')     # Teal for average
    else:
        patch.set_facecolor('#45B7D1')     # Blue for tall

# Add vertical line at the mean
mean_height = np.mean(heights)
plt.axvline(mean_height, color='red', linestyle='--', linewidth=2,
            label=f'Mean: {mean_height:.1f} cm')

# Titles and labels
plt.title('Distribution of Student Heights (200 Students)', fontsize=15, fontweight='bold')
plt.xlabel('Height (cm)', fontsize=12)
plt.ylabel('Number of Students', fontsize=12)
plt.legend(fontsize=11)
plt.grid(axis='y', alpha=0.3)

plt.tight_layout()
plt.show()
```

**📊 Expected Output:**  
A histogram with 20 bins showing the bell-curve shaped distribution of student heights. Most heights cluster around 160–170 cm (the tallest bars). A red dashed line marks the mean (average) height. The color coding distinguishes short, average, and tall students.

---

#### 🐍 Seaborn — Histogram

```python
# ============================================================
# SEABORN HISTOGRAM
# Same height data — Seaborn adds a smooth density curve automatically!
# ============================================================

# Create DataFrame
df_heights = pd.DataFrame({'Height_cm': heights})

plt.figure(figsize=(10, 6))

# histplot with kde=True adds both histogram AND a smooth density curve
sns.histplot(data=df_heights,
             x='Height_cm',
             bins=20,
             kde=True,           # KDE = Kernel Density Estimate (the smooth curve)
             color='steelblue',
             edgecolor='white',
             alpha=0.7,
             line_kws={'linewidth': 2.5, 'color': 'darkblue'})

# Add mean line
plt.axvline(df_heights['Height_cm'].mean(), color='red',
            linestyle='--', linewidth=2, label=f'Mean: {heights.mean():.1f} cm')

plt.title('Distribution of Student Heights — Seaborn with KDE', fontsize=15, fontweight='bold')
plt.xlabel('Height (cm)', fontsize=12)
plt.ylabel('Count', fontsize=12)
plt.legend(fontsize=11)
plt.grid(axis='y', alpha=0.3)

plt.tight_layout()
plt.show()
```

**📊 Expected Output:**  
The same histogram, but Seaborn has automatically added a smooth **KDE (Kernel Density Estimate) curve** in dark blue on top. This curve shows the overall shape of the distribution more clearly. The bell-curve shape confirms our data is normally distributed.

---

### 3.5 Pie Chart

#### 📖 Explanation

A **pie chart** is a circular graph divided into slices, where each slice represents a **proportion or percentage** of the whole. It's best used when you want to show **how a total is divided** among a few categories. Keep pie charts simple — too many slices make them hard to read!

#### 🎯 Use Case

- Showing market share of different smartphone brands
- Displaying what percentage of budget goes to different departments
- Illustrating the breakdown of a country's energy sources

---

#### 🐍 Matplotlib — Pie Chart

```python
# ============================================================
# MATPLOTLIB PIE CHART
# Favorite programming languages among 200 students
# ============================================================

# Data: survey results
languages = ['Python', 'JavaScript', 'Java', 'C++', 'Others']
votes = [85, 50, 30, 20, 15]

# Colors for each slice
colors = ['#FF9999', '#66B2FF', '#99FF99', '#FFCC99', '#C8A8E9']

# Which slice to "explode" (pull out) for emphasis
explode = (0.08, 0, 0, 0, 0)  # Slightly pull out the first slice (Python)

plt.figure(figsize=(9, 7))

# Create the pie chart
wedges, texts, autotexts = plt.pie(
    votes,
    labels=languages,
    colors=colors,
    explode=explode,
    autopct='%1.1f%%',     # Show percentage with 1 decimal place
    startangle=140,         # Start the first slice at 140 degrees
    pctdistance=0.85,       # Position of the percentage text inside the slice
    shadow=True             # Add a subtle shadow for depth
)

# Style the percentage text
for autotext in autotexts:
    autotext.set_fontsize(11)
    autotext.set_fontweight('bold')

# Title
plt.title('Favorite Programming Languages\nSurvey of 200 Students', 
          fontsize=15, fontweight='bold', pad=20)

plt.tight_layout()
plt.show()
```

**📊 Expected Output:**  
A colorful pie chart with 5 slices. Python has the largest slice (42.5%) and is slightly pulled out to emphasize it as the most popular language. Each slice shows its exact percentage. The shadow adds visual depth to the chart.

---

#### 🐍 Seaborn — Pie Chart

```python
# ============================================================
# SEABORN PIE CHART
# Note: Seaborn doesn't have a native pie chart function.
# Best practice: use Matplotlib for pie charts, even in Seaborn projects.
# Instead, we'll show a Seaborn DONUT CHART (a modern alternative!)
# ============================================================

# Data
languages = ['Python', 'JavaScript', 'Java', 'C++', 'Others']
votes = [85, 50, 30, 20, 15]

# Use Seaborn color palette
colors = sns.color_palette('pastel', len(languages))

fig, ax = plt.subplots(figsize=(9, 7))

# Create pie chart (donut style by adding a white circle in the center)
wedges, texts, autotexts = ax.pie(
    votes,
    labels=languages,
    colors=colors,
    autopct='%1.1f%%',
    startangle=140,
    pctdistance=0.80,
    wedgeprops=dict(width=0.6)  # This creates the donut hole!
)

# Style text
for autotext in autotexts:
    autotext.set_fontsize(11)
    autotext.set_fontweight('bold')

# Add text in the center of the donut
ax.text(0, 0, 'Languages\nSurvey', ha='center', va='center',
        fontsize=13, fontweight='bold', color='#333333')

ax.set_title('Favorite Programming Languages — Seaborn Palette (Donut Style)',
             fontsize=14, fontweight='bold', pad=20)

plt.tight_layout()
plt.show()

# ⚠️ IMPORTANT NOTE FOR BEGINNERS:
# Seaborn is built for statistical plots and doesn't support pie charts natively.
# For pie charts, use Matplotlib directly (as shown in section above).
# Seaborn's strength lies in distribution plots, regression plots, and heatmaps.
print("\n💡 Tip: For pie charts, Matplotlib is the better choice!")
```

**📊 Expected Output:**  
A modern donut-style chart using Seaborn's beautiful `pastel` color palette. The hole in the middle displays a label. This is a more modern and visually appealing alternative to traditional pie charts.

---

## 4. Matplotlib vs Seaborn: Head-to-Head Comparison

Now that you've seen both libraries in action, let's compare them across 5 important dimensions:

---

### 4.1 Ease of Use

| Aspect | Matplotlib | Seaborn |
|--------|-----------|---------|
| **Code length** | More verbose (more lines) | Concise (fewer lines) |
| **Learning curve** | Steeper — many parameters | Gentler — sensible defaults |
| **Working with DataFrames** | Requires extracting columns | Use column names directly |
| **Default output quality** | Plain-looking by default | Beautiful by default |

**Winner: 🏆 Seaborn** — Seaborn is easier and faster for beginners who want pretty charts quickly.

---

### 4.2 Customization

| Aspect | Matplotlib | Seaborn |
|--------|-----------|---------|
| **Control level** | Complete control over everything | High-level, less granular |
| **Custom layouts** | Very flexible (subplots, gridspec) | Moderate flexibility |
| **Fine-tuning** | Can adjust every pixel | Can use Matplotlib underneath |
| **Animations** | Supported | Not supported natively |

**Winner: 🏆 Matplotlib** — When you need pixel-perfect control or complex layouts, Matplotlib is unmatched.

---

### 4.3 Appearance (Default Styling)

| Aspect | Matplotlib | Seaborn |
|--------|-----------|---------|
| **Default style** | Plain, MATLAB-like | Modern, attractive |
| **Color palettes** | Basic colors by default | Rich built-in palettes |
| **Themes** | Requires manual styling | Multiple themes available |
| **Statistical aesthetics** | Manual | Automatic |

**Winner: 🏆 Seaborn** — Seaborn's plots look professional without any extra work.

---

### 4.4 Performance

| Aspect | Matplotlib | Seaborn |
|--------|-----------|---------|
| **Speed (small data)** | Fast | Slightly slower (due to computations) |
| **Speed (large data)** | Good | Can be slower (statistical calculations) |
| **Memory** | Efficient | Slightly higher |
| **Rendering complex plots** | More control over optimization | Less control |

**Winner: 🏆 Matplotlib** — For large datasets or performance-critical applications, Matplotlib is faster.

---

### 4.5 Best Use Cases

| Matplotlib is Best For | Seaborn is Best For |
|------------------------|---------------------|
| Custom, highly specific charts | Quick Exploratory Data Analysis (EDA) |
| Scientific papers requiring precision | Statistical visualizations |
| Animation and interactive plots | Presenting data science findings |
| Embedding in applications | Machine learning model insights |
| When you need complete control | When you want pretty charts fast |

---

### 4.6 Overall Summary Table

| Criteria | Matplotlib | Seaborn | Winner |
|----------|-----------|---------|--------|
| Ease of Use | ⭐⭐⭐ | ⭐⭐⭐⭐⭐ | Seaborn |
| Customization | ⭐⭐⭐⭐⭐ | ⭐⭐⭐ | Matplotlib |
| Default Appearance | ⭐⭐⭐ | ⭐⭐⭐⭐⭐ | Seaborn |
| Performance | ⭐⭐⭐⭐⭐ | ⭐⭐⭐⭐ | Matplotlib |
| Statistical Features | ⭐⭐⭐ | ⭐⭐⭐⭐⭐ | Seaborn |
| Beginner-Friendliness | ⭐⭐⭐ | ⭐⭐⭐⭐⭐ | Seaborn |
| Community & Resources | ⭐⭐⭐⭐⭐ | ⭐⭐⭐⭐ | Matplotlib |

---

## 5. Conclusion

### 5.1 Which Library is Better for Beginners?

**For absolute beginners, Seaborn is the recommended starting point.** Here's why:

1. You write **less code** and get **better-looking results** immediately
2. The **integration with Pandas** DataFrames makes it intuitive — just reference column names
3. **Built-in statistical features** teach you about data analysis while you visualize
4. The **beautiful default styles** make your projects look professional from day one
5. It's the most commonly used library in **data science interviews and portfolios**

### 5.2 The Professional Reality

In the real world, **data scientists use both libraries together**:

- Start with **Seaborn** for quick exploration and presentations
- Switch to **Matplotlib** when you need custom layouts, animations, or precise formatting
- Remember: Seaborn is built ON Matplotlib, so you can always mix them!

```python
# Example: Using both together
fig, axes = plt.subplots(1, 2, figsize=(14, 5))  # Matplotlib creates the layout

# Seaborn fills in the charts
sns.histplot(data=df_heights, x='Height_cm', ax=axes[0], kde=True, color='steelblue')
axes[0].set_title('Height Distribution')

sns.barplot(data=df_sales, x='Month', y='Books_Sold', ax=axes[1], palette='Set2')
axes[1].set_title('Monthly Book Sales')
axes[1].tick_params(axis='x', rotation=45)

plt.suptitle('Combined Dashboard: Matplotlib + Seaborn', fontsize=16, fontweight='bold')
plt.tight_layout()
plt.show()
```

### 5.3 Final Thoughts

Data visualization is one of the most valuable skills in data science. Whether you choose Matplotlib, Seaborn, or both — the key is **practice**. Start with simple charts, understand what each line of code does, and gradually build more complex visualizations.

> 🚀 **Your journey in data visualization has just begun! Keep exploring, keep plotting, and most importantly — have fun with your data!**

---

## 6. Steps to Run the Project

### Step 1: Set Up Your Environment

```bash
# Install Python (if not already installed)
# Download from: https://www.python.org/downloads/

# Install required libraries
pip install -r requirements.txt
```

### Step 2: Launch Jupyter Notebook

```bash
# Install Jupyter if needed
pip install jupyter

# Start Jupyter Notebook
jupyter notebook
```

### Step 3: Open the Notebook

1. In your browser, navigate to the project folder
2. Click on `visualization_guide.ipynb` to open it
3. Run cells one by one using **Shift + Enter**
4. Or click **"Run All"** from the Cell menu

### Step 4: Save Your Outputs

- After running all cells, your plots will appear inline
- Right-click any plot → **"Save image as"** to save screenshots
- Export the notebook: **File → Download as → HTML** for a shareable version

---

## 7. How to Upload to GitHub

### Step 1: Create a GitHub Account
Go to [github.com](https://github.com) and sign up for a free account.

### Step 2: Create a New Repository
1. Click the **"+"** icon → **"New repository"**
2. Name it: `shadowfox-dataviz-internship`
3. Set it to **Public**
4. Check **"Add a README file"**
5. Click **"Create repository"**

### Step 3: Upload Your Files

**Option A — Using GitHub Website (Easiest for Beginners):**
1. Open your repository
2. Click **"Add file"** → **"Upload files"**
3. Drag and drop all project files
4. Write a commit message: `"Add visualization guide and notebooks"`
5. Click **"Commit changes"**

**Option B — Using Git Command Line:**
```bash
# Initialize git in your project folder
git init

# Connect to your GitHub repository
git remote add origin https://github.com/YOUR_USERNAME/shadowfox-dataviz-internship.git

# Add all files
git add .

# Save your changes with a message
git commit -m "Add ShadowFox Data Visualization Guide"

# Upload to GitHub
git push -u origin main
```

---

## 8. Suggested Screenshots for Internship Submission

Take screenshots of the following for your internship submission:

| # | Screenshot | What to Capture |
|---|-----------|-----------------|
| 1 | **Setup** | Jupyter Notebook with setup cell executed successfully |
| 2 | **Line Plot** | Both Matplotlib and Seaborn line plots side by side |
| 3 | **Bar Chart** | Both bar charts showing monthly sales |
| 4 | **Scatter Plot** | Seaborn scatter with regression line and confidence interval |
| 5 | **Histogram** | Seaborn histogram with KDE curve |
| 6 | **Pie Chart** | Matplotlib pie chart and Seaborn donut chart |
| 7 | **Combined Dashboard** | The final combined Matplotlib + Seaborn subplot |
| 8 | **GitHub Repository** | Your repository page showing all uploaded files |
| 9 | **Notebook Overview** | Full Jupyter Notebook with all cells executed |

> 💡 **Pro Tip:** Use your computer's built-in screenshot tool (Snipping Tool on Windows, Cmd+Shift+4 on Mac) to capture clean screenshots of each plot.

---

*Document prepared for ShadowFox Data Science Internship*  
*Guide covers: Matplotlib | Seaborn | Data Visualization | Python | Jupyter Notebook*
