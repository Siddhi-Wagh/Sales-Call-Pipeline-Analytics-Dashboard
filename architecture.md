# 🏗️ Solution Architecture

## End-to-End Architecture

```text
┌───────────────────────────┐
│   Daily Call Data Files   │
│      (Recurring Data)     │
└─────────────┬─────────────┘
              │
              ▼
┌───────────────────────────┐
│     Folder Connector      │
│         Power BI          │
└─────────────┬─────────────┘
              │
              ▼
┌───────────────────────────┐
│       Combine Files       │
│  Consolidate Daily Data   │
└─────────────┬─────────────┘
              │
              ▼
┌───────────────────────────┐
│        Power Query        │
│                           │
│  Clean & Transform Data   │
└─────────────┬─────────────┘
              │
              ▼
┌───────────────────────────┐
│       Power BI Model      │
│                           │
│  Tables & Relationships   │
└─────────────┬─────────────┘
              │
              ▼
┌───────────────────────────┐
│       DAX Measures        │
│                           │
│  KPIs & Calculations      │
└─────────────┬─────────────┘
              │
              ▼
┌───────────────────────────┐
│    Power BI Dashboard     │
│                           │
│  Interactive Analytics    │
└─────────────┬─────────────┘
              │
              ▼
┌───────────────────────────┐
│     Power BI Service      │
│                           │
│ Publish & Scheduled Refresh│
└─────────────┬─────────────┘
              │
              ▼
┌───────────────────────────┐
│       Workspace           │
│                           │
│   Manage & Organize       │
└─────────────┬─────────────┘
              │
              ▼
┌───────────────────────────┐
│       Power BI App        │
│                           │
│   Share with Team Users   │
└───────────────────────────┘
```

---

## 🔄 Data Processing Flow

```text
Daily Files
    │
    ▼
Folder Connector
    │
    ▼
Combine Queries
    │
    ▼
Power Query
    │
    ▼
Cleaned Dataset
    │
    ▼
Data Model
    │
    ▼
DAX Calculations
    │
    ▼
Interactive Dashboard
```

### Purpose of Each Layer

| Layer | Purpose |
|---|---|
| Data Source | Recurring daily call data |
| Folder Connector | Access multiple files automatically |
| Combine Files | Consolidate files into a single dataset |
| Power Query | Clean and transform data |
| Data Model | Organize data for analysis |
| DAX | Create KPIs and calculations |
| Dashboard | Visualize and analyze data |

---

## ☁️ Deployment & Distribution Flow

```text
Power BI Desktop
       │
       │ Publish
       ▼
Power BI Service
       │
       ├──────────────► Scheduled Refresh
       │
       ▼
   Workspace
       │
       │ Publish
       ▼
  Power BI App
       │
       ▼
 Business Users
```

---

## 🔑 Key Architecture Decisions

### 1. Folder-Based Data Ingestion

Used Power BI Folder Connector to process recurring daily call data files through a repeatable workflow instead of importing files individually.

### 2. Centralized Data Transformation

Used Power Query as the primary transformation layer before loading data into the Power BI model.

### 3. Semantic & Calculation Layer

Used the Power BI data model and DAX measures to create reusable KPIs and analytical calculations.

### 4. Cloud-Based Reporting

Published the completed report to Power BI Service to support centralized report management and scheduled data refresh.

### 5. Controlled Distribution

Used a Workspace and Power BI App to provide team members with access to the reporting solution.

## 📌 Architecture Summary

The solution follows a complete Business Intelligence workflow:

**Ingest → Transform → Model → Calculate → Visualize → Publish → Refresh → Distribute**

This architecture enables recurring sales call data to be processed and delivered as interactive Power BI reporting for business users.
