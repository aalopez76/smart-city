# smart-city
Predictive analytics &amp; RL for traffic, climate and energy in smart cities

End-to-end platform that ingests real-time traffic, weather and social data,
predicts congestion & energy demand, and recommends traffic-light timing 
to reduce CO₂.

```mermaid
flowchart LR
  A[APIs & Sensors] -->|Kafka| B(Raw Lake S3/MinIO)
  B --> C[ETL Spark/DuckDB]
  C --> D[Feast Feature Store]
  D --> E1[Traffic TFT]
  D --> E2[Graph GNN]
  E1 & E2 --> F(KServe Micro-services)
  F --> G[Streamlit Dashboard]
