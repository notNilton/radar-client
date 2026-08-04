# 📋 Radare Platform Roadmap & TODOs

Roadmap for **Radare** (Industrial Data Reconciliation & Statistical Validation Platform).

---

## 🧮 1. Reconciliation Algorithms & Advanced Statistics
- [x] **Genetic Algorithm & Robust M-Estimators**
  - Implemented in  (Huber, Fair, Genetic Solver).
- [ ] **Expose Advanced Solvers REST APIs**
  - Add API endpoints allowing users to select between Lagrange Solver and Genetic / M-Estimator Solvers.
- [ ] **Drift Metrics Persistence (CUSUM / EWMA)**
  - Store drift detection history in LogDB and issue real-time alerts upon deviation.
- [ ] **Data Fuzzing & Monte Carlo Simulation (ISO GUM)**
  - Synthetic noise injection engine and confidence interval calculation for empirical validation.

---

## ⚙️ 2. Backend & Data Ingestion
- [ ] **Live MQTT Ingestion Pipeline**
  - Consume live industrial tag readings via production broker.
- [ ] **InfluxDB Time-Series Integration**
  - Persist reconciled time-series historical data.
- [ ] **Prometheus Metrics Exporter**
  - Native  endpoint for system health and solver observability.

---

## 💻 3. Webapp & User Interface (React / Vite)
- [ ] **Graph Topology Diff Viewer**
  - UI interface to compare changes between plant process model versions.
- [ ] **Executive Report Exporting (CSV / Excel / PDF)**
  - Download reconciled mass and energy balance reports.

---

## 🗄️ 4. Database & Infrastructure
- [ ] **Monthly PostgreSQL Table Partitioning (Partition Pruning)**
  - Table partitioning strategy for historical reconciliation logs.
- [ ] **GitHub Actions CI/CD Pipelines**
  - Automated testing for Go, Vitest, and Docker build validations.
