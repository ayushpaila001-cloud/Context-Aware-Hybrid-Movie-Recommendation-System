#  Context-Aware Hybrid Movie Recommendation System

## Reducing Decision Fatigue using Content-Based Filtering, Collaborative Filtering, and Context-Aware Personalization

# Project Summary

With the rapid growth of OTT (Over-the-Top) streaming platforms, users are presented with thousands of movies and TV shows across multiple genres, languages, and platforms. While recommendation systems have become an integral part of these platforms, many existing systems rely heavily on historical watch history or popularity-based suggestions. As a result, users often spend a considerable amount of time browsing before selecting content, a phenomenon commonly referred to as **decision fatigue**.
This project presents a **Context-Aware Hybrid Movie Recommendation System** that combines **Content-Based Filtering**, **User-Based Collaborative Filtering**, and **Context-Aware Personalization** to recommend movies that align with both a user's long-term preferences and their current viewing situation.
Unlike traditional recommendation systems, this project incorporates behavioral analytics, user preferences, watch history, and real-time contextual information such as mood, available viewing time, time of day, and viewing companion. By integrating these factors, the recommendation engine generates personalized suggestions while reducing the cognitive effort involved in selecting content.
The project also introduces a **Decision Fatigue Score**, developed using user survey responses, to better understand browsing behavior and quantify the difficulty users face while choosing content.

# Problem Statement

Modern streaming platforms provide users with an enormous selection of content. While this abundance offers greater choice, it also creates a significant challenge users often struggle to decide what to watch.
Several common problems observed among OTT users include:

- Spending excessive time browsing before selecting content.
- Receiving repetitive recommendations based solely on watch history.
- Recommendations that fail to reflect the user's current mood or situation.
- Difficulty discovering new content despite personalized recommendations.
- Decision fatigue caused by an overwhelming number of available options.

Traditional recommendation systems generally consider historical viewing behavior but overlook the influence of contextual factors such as available time, viewing companions, or emotional state.

This project aims to answer the following question:
**Can a Context-Aware Hybrid Recommendation System improve recommendation quality by combining user preferences, content similarity, collaborative filtering, and contextual information while simultaneously reducing decision fatigue?**

# Dataset Description
The recommendation engine was developed using five datasets, each representing a different component of an OTT streaming platform.

### OTT User Survey Dataset
The survey dataset contains approximately one thousand responses collected to understand user behavior while using OTT platforms.

The survey includes information related to:

- Watch frequency
- Time spent deciding what to watch
- Number of titles browsed
- Recommendation satisfaction
- Content discoverability
- Runtime preference
- Viewing habits
- Choice overload
- Decision fatigue

This dataset was primarily used for exploratory analysis and the calculation of the Decision Fatigue Score.

### Content Dataset

The content dataset consists of metadata describing sixty-five movies and web series.
Each title includes attributes such as:

 - Genre
- Language
- Runtime Category
- Mood
- Complexity
- Release Period
- OTT Platform
- Popularity Tier
- Content Type

These attributes were transformed into numerical feature vectors to support content-based recommendations.

### User Preference Dataset

The user preference dataset represents long-term viewing preferences for approximately two hundred users.
Each profile includes:

- Favourite Genres
- Preferred Languages
- Preferred OTT Platforms
- Preferred Content Types
- Complexity Preference

These preferences were converted into numerical vectors that could be directly compared with movie feature vectors.

### User Watch History

The watch history dataset contains approximately four thousand viewing records.
This dataset enables the recommendation engine to:

- Identify previously watched content.
- Prevent duplicate recommendations.
- Learn historical viewing behavior.
- Support collaborative recommendation.

### Current Session Dataset

This dataset captures the user's real-time viewing context.
The contextual features include:

- Current Mood
- Available Watching Time
- Viewing Companion
- Time of Day
- Weekday or Weekend

These features allow recommendations to adapt dynamically according to the user's current situation.

# Data Preprocessing
A structured preprocessing pipeline was implemented before building the recommendation engine.
The preprocessing workflow included:

- Removing duplicate records.
- Handling missing values.
- Standardizing categorical variables.
- Cleaning inconsistent entries.
- Formatting datasets for machine learning.

# Feature Engineering

To make the datasets compatible with machine learning algorithms, several feature engineering techniques were applied.
Categorical variables were transformed using **One-Hot Encoding**.
Separate feature vectors were created for:

- Movies
- Users

Both vectors were designed to exist within the same feature space, allowing direct similarity calculations using cosine similarity.

# Exploratory Data Analysis (EDA)

Comprehensive exploratory data analysis was conducted to understand user behavior and identify the major factors contributing to decision fatigue.
The analysis focused on:

- User watch frequency
- Average decision time
- Recommendation satisfaction
- Runtime preferences
- Choice overload
- Content discoverability
- OTT platform preferences
- User browsing behavior

Several visualizations were created throughout the analysis, including:
- Histograms
- Bar Charts
- Pie Charts
- Correlation Heatmaps
- Cross-tabulation Analysis

These insights helped guide the design of the recommendation engine.

# Decision Fatigue Score
One of the key contributions of this project is the development of a custom **Decision Fatigue Score**.
The score quantifies how difficult users find the process of selecting content on OTT platforms.
The score was calculated using five behavioural indicators:

- **Decision Time (30%)** – Time spent deciding what to watch.
- **Titles Browsed (25%)** – Number of titles explored before making a decision.
- **Recommendation Clarity (20%)** – How clearly users knew what they wanted to watch.
- **Choice Overload (15%)** – The extent to which excessive content made decision-making difficult.
- **Skipping Long Content (10%)** – User tendency to avoid longer movies or series during browsing.

Based on the final score, users were classified into four fatigue categories:

- Low Fatigue
- Moderate Fatigue
- High Fatigue
- Severe Fatigue

# Machine Learning Methodology

Since no single recommendation technique can effectively capture every aspect of user behavior, this project adopts a hybrid recommendation strategy.

### Content-Based Filtering

Content-Based Filtering recommends movies that share similar characteristics with content previously preferred by the user.
Movie similarity is determined using features such as:

- Genre
- Language
- Runtime
- Mood
- Complexity
- Popularity
- Platform

### User-Based Collaborative Filtering

Collaborative Filtering identifies users with similar viewing preferences.
Rather than recommending movies solely based on content similarity, it also considers what similar users have enjoyed.
This helps improve recommendation diversity while reducing over-specialization.

### Context-Aware Recommendation

One of the primary objectives of this project was to incorporate real-time contextual information into the recommendation process.
The recommendation engine adapts according to:

- Current Mood
- Available Viewing Time
- Viewing Companion
- Preferred Language
- Time of Day
- Weekday or Weekend

These contextual signals allow recommendations to change dynamically according to the user's current situation.

# Recommendation Pipeline

The recommendation engine follows the workflow below:

Survey Data
      │
Exploratory Data Analysis
      │
Decision Fatigue Analysis
      │
Feature Engineering
      │
Content Vector Construction
      │
User Preference Vector Construction
      │
Cosine Similarity Calculation
      │
Generate Candidate Movies
      │
Apply Context-Aware Hybrid Scoring
      │
Remove Previously Watched Movies
      │
Generate Top-N Personalized Recommendations

# Hybrid Recommendation Strategy

Each candidate movie receives a final recommendation score based on multiple weighted factors.
The recommendation engine considers:

- Content similarity between the movie and the user's preferences.
- Current mood compatibility.
- Duration suitability based on available viewing time.
- Viewing companion preferences.
- Weekday or weekend viewing patterns.
- Preferred language.
- Time of day.

The highest-scoring unseen movies are returned as personalized recommendations.

# Statistical Validation

To validate the behavioral insights obtained during exploratory analysis, Chi-Square Tests of Independence were performed.
The statistical analysis examined relationships such as:

- Decision Fatigue versus Recommendation Satisfaction.
- Decision Fatigue versus Exit Without Watching.
- Decision Fatigue versus AI Recommendation Acceptance.

These analyses confirmed meaningful behavioral patterns within the survey data.
# Technologies Used

The project was developed using the following technologies:

- Python
- Pandas
- NumPy
- Scikit-learn
- SciPy
- Matplotlib
- Seaborn
- OpenPyXL
- Jupyter Notebook

# Key Skills Demonstrated

Throughout this project, the following technical skills were applied:

- Exploratory Data Analysis (EDA)
- Data Cleaning and Preprocessing
- Feature Engineering
- One-Hot Encoding
- Recommendation System Design
- Content-Based Filtering
- Collaborative Filtering
- Context-Aware Machine Learning
- Cosine Similarity
- Statistical Analysis
- User Behaviour Analytics
- Data Visualization
- Machine Learning Pipeline Development


# Data Availability

The datasets used in this project were developed for academic and research purposes to simulate user behaviour on OTT platforms.
The complete recommendation workflow, machine learning pipeline, feature engineering methodology, and analysis are included in this repository for educational purposes.


# License

This project is licensed under the **MIT License**.

Feel free to use, modify, and extend this project for academic, research, and learning purposes.
