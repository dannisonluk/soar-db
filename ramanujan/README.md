# Ramanujan

## 🚀 Overview

**Ramanujan** is a robust, high-performance data processing system designed to handle **massive business and financial datasets** with exceptional efficiency and scalability.  

Built on **Apache Spark (Java API)**, it provides end-to-end capabilities for data **ingestion**, **pre-processing**, **cleaning**, **transformation**, and **feature engineering** to support downstream **analytics** and **machine learning** workloads.

The system is optimized for large-scale data pipelines, typically managing inputs **exceeding 20GB per dataset**.

Processed data available on Oracle DB is consumed by the **API module of the `soar-db` project**.

---

## ✨ Key Capabilities

- **High-Throughput Data Handling**  
  Optimized for distributed processing of very large datasets.

- **Core Framework**  
  Powered by the **Java API for Apache Spark**, providing low-latency execution, high reliability, and type safety.

- **Optimized I/O Performance**  
  Utilizes **Parquet** columnar storage, reducing run and processing times by **90%+** with Spark-optimized modules.

- **Advanced Business Logic Integration**  
  Specialized modules for:
    - **Hierarchical Data Grouping**: Grouping by temporal units (year/month/week), airline, airport, region, OD pairs, etc.
    - **Schema Validation and Enforcement**: Strict validation to ensure data integrity before transformation.
    - **Normalization and Standardization**: Harmonizing heterogeneous data sources for unified analysis.
    - **Time-Series Aggregation**: Efficient computation of daily/periodical financial metrics.

- **Financial Data Pre-processing Engine**  
  Tailored features for market datasets:
    - **Market Volatility Outlier Detection**
    - **Feature Engineering** (e.g., moving averages, volatility measures)
    - **Event-Impact Correlation** (linking market events with performance indicators)

- **Machine Learning on Inventory and Risk Analysis**  
    - Refer to ```Core Processing Modules```
---

## 🛠️ Tools and Dependencies

| Component          | Description                      |
|:-------------------|:---------------------------------|
| **Core Framework** | Apache Spark (Java API), PyTorch |
| **Language**       | Java 1.8, Python 3.12            |
| **Build Tool**     | Maven, Pip                       |
| **Data Storage**   | Oracle DB, Local Storage         |

---

## 💻 Modules

The system’s logic is implemented through declarative **Spark Transformations** and **User Defined Functions (UDFs)** to maximize distributed performance.

### Core Processing Modules

- **Market Supply Data (Capacity)**  
  Processes freighter market supply data for operational and strategic planning.

- **Market Demand Data (Demand)**  
  Ingests and transforms global demand figures to support forecasting.

- **Financial Index Reference**  
  Reviews macroeconomic indicators (freight indices, shipment statistics, confidence metrics).

- **API Layer**  
  Works with the `soar-db` project to expose processed datasets via defined endpoints.

- **Machine Learning for Market Analysis and Inventory Management**  
  Organized into two sub-modules:
    - **Support Vector Machine (SVM)** >> **kernel='rbf'**
        - Supply vs Demand Analysis
        - Inventory Risk Alerting
    - **Deep Q-Network (DQN)** >> **Pending to start in November**
        - Inventory Management
        - Pricing Recommendations (adaptive to supply-demand fluctuations)

---

## 💾 Storage

Data persistence is structured for performance and cost efficiency:

- **Cloud Storage (Optimized)**  
  Stores processed, aggregated datasets grouped by airline, airport, OD pairs, region, and time.  
  Designed for **fast queries** by end-user applications, including financial indices.

- **Local Storage (Archive)**  
  Retains **raw, untransformed data** for historical analysis and ad-hoc reporting.  
  Running scripts are provided for analytics and retrospective studies.

---

## 📬 Intellectual Property Notice

If any part of this system (code, documentation, or data handling process) is found to conflict with existing company interests, proprietary rights, or third-party copyrights:
- Please **notify the developer immediately**.
- The conflicting element will be reviewed and either revised or removed promptly.
