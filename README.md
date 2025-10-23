# Mario ETL Personal Project

Welcome to the Mario ETL Personal Project for IS 640! This hands-on, graduate-level assignment guides you through building a complete data pipeline using the Medallion Architecture. You'll transform raw Mario game data into analytics-ready reports, learning best practices in data engineering and analytics along the way.

---

## � Project Overview

This ETL project demonstrates an end-to-end data pipeline, leveraging the Medallion Architecture to consolidate multiple spreadsheets from a folder into a unified DataFrame (DF). Each data layer transforms the dataset progressively, allowing for streamlined data processing and enhanced analytics capabilities.

### Medallion Architecture Layers

- **Bronze Layer:** Raw data ingestion and minimal processing
- **Silver Layer:** Data cleaning, validation, and transformation
- **Gold Layer:** Advanced analytics and reporting

---

## �📋 Project Requirements

1. **Download** the Mario ETL.zip file and extract its contents.
2. **Create** three Jupyter Notebooks, one for each Medallion layer: Bronze, Silver, and Gold.
3. **Submit** the required Parquet files for each layer and report.
4. **Deliverables:**
   - 3 Notebooks: `Bronze_Mario.ipynb`, `Silver_Mario.ipynb`, `Gold_Mario.ipynb`
   - 12 Parquet files: Bronze, Silver, and 10 Gold reports

---

## 🥉 Bronze Layer: Data Ingestion & Initial Processing

**Objective:** Ingest and consolidate raw data

Tasks:

- Combine all CSV and JSONL files into a single DataFrame
- Save the unified DataFrame in Parquet format as `Bronze.parquet`

---

## 🥈 Silver Layer: Data Cleaning & Transformation

**Objective:** Clean, validate, and standardize the data

### Data Cleaning Steps

1. **Fill null values** with smart categories for columns:
   - Player Name
   - Team
   - Kart Racing Rank
   - Mushroom Cup Participation
2. **Remove punctuation errors** from the "Kart Role" column
3. **Detect and list misspellings** in the "Player Name" column (show all similar names with >80% similarity)
4. **Format columns** to correct data types:
   - Player Name: `string`
   - Team: `string`
   - Kart Racing Rank: `string`
   - Mushroom Cup Participation: `bool`
   - Participation in Battle Mode: `bool`
   - Platforming Rank: `string`
   - Boss Battle Rank: `string`
   - Power-Ups Owned: `string`
   - Power-Ups Used: `int32`
   - Team Points: `int32`
   - Levels Completed: `int32`
   - Lives Lost: `int32`
   - Times Hit by Enemies: `int32`
   - Vehicle Type: `string`
   - World: `string`
   - Coins Spent in Toad Town: `int32`
   - Companion: `string`
   - Primary Game: `string`
   - Kart Role: `string`
5. **Check and correct Mario-related misspellings** in "Player Name"
6. **Standardize player names** using the official list:
   - Mario, Luigi, Peach, Daisy, Yoshi, Toad, Toadette, Rosalina, Wario, Waluigi, Bowser, Bowser Jr.
7. **Remove leading/trailing spaces** from:
   - Vehicle Type
   - World
   - Primary Game
8. **Apply title case** to:
   - Team
   - Companion
   - World

---

## 🥇 Gold Layer: Analytics & Reporting

**Objective:** Generate actionable insights and reports

Create the following 10 Gold Reports (each saved as a Parquet file):

1. **Team Performance Summary**
   - Total team points, average rank, and total coins spent in Toad Town by team
   - _Rank scoring:_ `{'S': 5, 'A': 4, 'B': 3, 'C': 2, 'D': 1}`
2. **Player Performance**
   - Total team points earned by each player (sorted by points descending)
3. **Power-Up Analytics**
   - Count and average number of power-ups used per player
4. **World Difficulty Analysis**
   - Average number of lives lost in each world (descending order)
5. **Top Performers**
   - Top player per team by team points
6. **Vehicle Popularity**
   - Popularity count of each vehicle type
7. **Risk Assessment**
   - Players at highest risk (total lives lost, sorted most to least)
8. **World Completion Stats**
   - Average and total number of levels completed in each world
9. **Team Combat Analysis**
   - Total and average number of times each team was hit by enemies
10. **Spending Analysis**
    - Total coins spent in Toad Town by each team

---

## 📤 Submission Checklist

### Parquet Files

**Core Files:**

- `Bronze.parquet`
- `Silver.parquet`

**Gold Report Files:**

- `gold_team_summary.parquet`
- `gold_player_performance.parquet`
- `gold_powerup_player.parquet`
- `gold_world_difficulty.parquet`
- `gold_top_player_per_team.parquet`
- `gold_vehicle_counts.parquet`
- `gold_risk_assessment.parquet`
- `gold_world_completion.parquet`
- `gold_hits_team.parquet`
- `gold_spending_analysis.parquet`

### Jupyter Notebooks

- `Bronze_Mario.ipynb`
- `Silver_Mario.ipynb`
- `Gold_Mario.ipynb`

---

## 🏆 Medallion Architecture Overview

The Medallion Architecture offers a structured approach to data transformation, consisting of three key layers: Bronze, Silver, and Gold. This architecture provides an incremental pathway from raw data ingestion to refined, analytics-ready datasets.

### Bronze Layer 🥉

Represents the raw, unprocessed data. Data is ingested "as is," with minimal transformations. The goal is to retain the original form of the data while accommodating various sources, including spreadsheets, servers, APIs, and more.

### Silver Layer 🥈

Data undergoes cleansing and validation to enhance quality. This layer provides a structured, reliable dataset suitable for further analysis. Silver tables are often used across the organization to support business intelligence (BI) and reporting needs.

### Gold Layer 🥇

Focuses on creating polished datasets optimized for analytics and reporting. Using data from the Silver Layer, this stage involves transformations, aggregations, and business logic that tailor the data for stakeholders' insights and decision-making. Gold Layer tables are integrated into BI tools like Power BI or Tableau, especially valuable for large datasets.

---

## 📚 References

- [Databricks Medallion Architecture Documentation](https://www.databricks.com/glossary/medallion-architecture)
- [Microsoft Medallion Architecture Documentation](https://learn.microsoft.com/en-us/azure/databricks/lakehouse/medallion)

---

_Good luck with your Mario ETL project! May your pipeline be fast and your insights be golden! 🎮_
