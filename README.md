# PlayerForge

PlayerForge is a **Databricks-based gaming analytics and RAG system** that processes synthetic gaming telemetry to generate player-performance insights. The project uses **PySpark, Delta Lake, Databricks SQL, vector search, and LLMs** to transform raw match data into structured analytics and natural-language answers.

The system follows a **Bronze → Silver → Gold** data architecture, where raw telemetry is cleaned and transformed into analytical datasets containing player, combat, map, role, MVP, and win-rate statistics.

<p align="center">
  <img
    src="https://github.com/user-attachments/assets/58f91168-7f22-4c32-9cd7-65827451c6e8"
    alt="PlayerForge"
    width="800"
  />
</p>

## Table of Contents

* [Features](#features)
* [Architecture](#architecture)
* [Key Analytics](#key-analytics)
* [Tech Stack](#tech-stack)
* [Installation](#installation)
* [Usage](#usage)
* [Example Queries](#example-queries)
* [Data Layers](#data-layers)
* [Contributing](#contributing)
* [License](#license)

## Features

* Processes synthetic gaming match and player telemetry using **PySpark**
* Implements a **Bronze, Silver, and Gold** data architecture using Delta Lake
* Cleans, validates, and transforms raw gaming data
* Generates analytical datasets for player and match performance
* Uses **SQL** for structured performance analysis
* Calculates player metrics such as win rate, K/D ratio, kills per match, and performance score
* Builds a knowledge base containing gameplay and performance concepts
* Uses **HuggingFace Embeddings and FAISS** for semantic retrieval
* Combines retrieved contextual information with structured player statistics
* Uses an **LLM-based RAG pipeline** to answer natural-language gaming analytics questions

## Architecture
<p align="center">
  <img
    src="https://github.com/user-attachments/assets/06f8134a-ab19-4d01-a2aa-4a489b325c38"
    alt="PlayerForge Architecture"
    width="800"
  />
</p>

## Key Analytics

* **Win Rate** – Percentage of matches won by a player
* **K/D Ratio** – Relationship between kills and deaths
* **Kills per Match** – Average number of kills per match
* **Goals per Match** – Average goals scored per match
* **Assists per Match** – Average assists generated per match
* **Performance Score** – Composite measure of player performance
* **Game-Mode Statistics** – Performance analysis across different game modes
* **Role Statistics** – Performance comparison across gameplay roles

## Tech Stack

* **Python** – Data processing and RAG pipeline
* **PySpark** – Distributed data processing and transformation
* **Databricks** – Data engineering, analytics, and execution environment
* **Delta Lake** – Reliable storage for Bronze, Silver, and Gold data layers
* **Databricks SQL** – Analytical queries and performance metrics
* **Hugging Face Embeddings** – Text embeddings for semantic retrieval
* **FAISS** – Vector similarity search
* **LLM / Gemini API** – Natural-language response generation
* **Git** – Version control

## Installation

### Prerequisites

The project requires access to a **Databricks workspace** with a compatible cluster or compute environment.

You should also have:

* Python 3.x
* PySpark
* Databricks Runtime
* Sentence Transformers
* FAISS
* OpenAI API access

### Clone the Repository

```bash
git clone https://github.com/HarshtheGeek/PlayerForge-Gaming-Analytics-RAG-Assistant.git
cd PlayerForge-Gaming-Analytics-RAG-Assistant
```

### Install Python Dependencies

Install the required packages in your Databricks environment:

```bash
pip install pyspark
pip install faiss-cpu
pip install openai
```

> Package requirements may vary depending on the Databricks Runtime being used.

## Usage

### 1. Load the Gaming Data

Upload or make the synthetic gaming telemetry available in the Databricks environment.

### 2. Build the Data Layers

Process the raw data through the Bronze, Silver, and Gold layers.

```text
Raw Data
   ↓
Bronze
   ↓
Silver
   ↓
Gold
```

The Gold layer contains analytical tables that can be queried directly from Databricks notebooks or SQL.

### 3. Query Gold Tables

Example PySpark usage:

```python
gold_tables = [
    "playerforge.gold.combat_stats",
    "playerforge.gold.map_stats",
    "playerforge.gold.mvp_stats",
    "playerforge.gold.player_stats",
    "playerforge.gold.role_stats",
    "playerforge.gold.win_rate_stats"
]

for table in gold_tables:
    print(f"\n===== {table} =====")
    spark.table(table).printSchema()
```

### 4. Run Analytical Queries

Gold tables can be queried using Databricks SQL or Spark SQL.

Example:

```sql
SELECT
    player_id,
    win_rate,
    kd_ratio,
    kills_per_match
FROM playerforge.gold.combat_stats
ORDER BY kd_ratio DESC
LIMIT 10;
```

### 5. Run the RAG Pipeline

The RAG pipeline retrieves relevant gameplay and performance context using semantic similarity and combines it with structured player statistics.

```text
User Query
    ↓
Query Embedding
    ↓
FAISS Retrieval
    ↓
Relevant Knowledge
    +
Player Statistics
    ↓
LLM
    ↓
Contextual Answer
```

## Example Queries

The system can answer questions such as:

```text
Who has the highest win rate?

Which players have the strongest attacking performance?

Which players demonstrate the strongest combat efficiency?

What factors indicate strong player engagement?

Why is Player 101 considered a strong attacker?

Compare two players and explain the difference in their performance.
```

<p align="center">
  <img
    src="https://github.com/user-attachments/assets/b21d72d1-2f90-43c5-81d6-fe65d181cb37"
    alt="PlayerForge"
    width="800"
  />
</p>


## Data Layers

### Bronze Layer

The Bronze layer stores the **raw gaming telemetry** with minimal transformation.

Typical data includes:

* Player information
* Match information
* Kills and deaths
* Goals and assists
* Match duration
* Game mode
* Player role
* Match outcome

### Silver Layer

The Silver layer contains **cleaned and validated data**.

Processing includes:

* Data type corrections
* Null handling
* Duplicate removal
* Data validation
* Standardization
* Derived fields

### Gold Layer

The Gold layer contains **business-ready analytical datasets** designed for player-performance analysis.

Current analytical tables include:

```text
playerforge.gold.combat_stats
playerforge.gold.map_stats
playerforge.gold.mvp_stats
playerforge.gold.player_stats
playerforge.gold.role_stats
playerforge.gold.win_rate_stats
```

These tables provide the structured foundation for the analytics and RAG components.

## RAG Architecture

PlayerForge combines **structured retrieval** and **semantic retrieval** rather than relying exclusively on an LLM.

```text
                    User Question
                         │
              ┌──────────┴──────────┐
              ▼                     ▼
       Structured Data        Knowledge Base
              │                     │
       Gold Delta Tables      Text Embeddings
              │                     │
              │                   FAISS
              │                     │
              └──────────┬──────────┘
                         ▼
                    Context Builder
                         │
                         ▼
                         LLM
                         │
                         ▼
                 Final Answer
```

This approach allows the system to combine **numerical player statistics** with **contextual gameplay knowledge**, producing explanations rather than simply returning raw database values.

## Contributing

1. Fork the repository
2. Create a feature branch:

```bash
git checkout -b feature/YourFeature
```

3. Commit your changes:

```bash
git commit -m "Add some feature"
```

4. Push the branch:

```bash
git push origin feature/YourFeature
```

5. Open a Pull Request

## License

This project is licensed under the MIT License – see the [LICENSE](LICENSE) file for details.

> **Dataset:** Synthetic gaming telemetry created for demonstration and learning purposes. No proprietary EA Sports data is used.
