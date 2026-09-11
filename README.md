# PlayerForge-Gaming-Analytics-RAG-Assistant

A **Databricks-based gaming analytics project** that processes synthetic match telemetry using PySpark and Delta Lake, builds player-performance analytics with SQL, and uses RAG to provide contextual insights through natural-language queries.

## What It Does

* Ingests synthetic gaming match and player data into Databricks
* Cleans and validates data using PySpark
* Implements **Bronze, Silver, and Gold** data layers with Delta Lake
* Generates player performance and engagement metrics
* Uses Databricks SQL for analytical queries
* Builds a knowledge base for gameplay and performance concepts
* Uses **Sentence Transformers + FAISS** for semantic retrieval
* Combines structured player statistics with retrieved context using an LLM

## Key Analytics

* Win rate
* Goals per match
* Assists per match
* Performance score
* Average match duration
* Player engagement
* Abandonment rate
* Game-mode statistics

## Example Queries

```text
Who has the highest win rate?

Which players have the strongest attacking performance?

What factors indicate strong player engagement?

Why is Player 101 considered a strong attacker?

Compare two players and explain the difference in their performance.
```

## Tech Stack

**Python · PySpark · Databricks · Delta Lake · SQL · Sentence Transformers · FAISS · OpenAI API · Git**

> **Dataset:** Synthetic gaming telemetry created for demonstration purposes. No proprietary EA data is used.
