# 📋 Radare Platform - Master Roadmap & TODOs

Visão geral da organização e acompanhamento de tarefas da plataforma **Radare** (Reconciliação de Dados Industriais & Validação Estatística).

---

## 🏗️ Estrutura de Organização do Projeto

A organização de tarefas do **Radare** é dividida por **Fases de Maturidade** (localizadas em `docs/planning/`):

- **Fases 1 a 5 (Concluídas ✅)**: MVP, Arquitetura Go + React, Persistência de Grafos, WebSockets, Dual Database (PostgreSQL + LogDB), Workers MQTT/InfluxDB, RBAC e PWA.
- **Fase 6 (Em Progresso ⚡)**: Otimização Heurística, Algoritmo Genético, Filtros CUSUM/EWMA e M-Estimadores Robustos (Huber/Fair).
- **Fase 7 (Planejada 🛡️)**: Data Fuzzing, Simulações Monte Carlo (ISO GUM) e Benchmarking Estatístico para Publicação.

---

## ⚡ Fase 6: Otimização Heurística & Algoritmos Avançados (Atual)

- [x] **Genetic Algorithm Solver (Go)**
  - Implementado em `internal/reconciliation/heuristics/` com harness comparativo contra o solver de Lagrange.
- [x] **Constraint Programming & Penalidades**
  - Resolução de desigualdades físicas via penalidade no solver genético.
- [x] **Detecção de Drift com CUSUM/EWMA**
  - Filtros CUSUM/EWMA implementados para detecção de desvio gradual em sensores.
- [x] **Baseline Robusto com M-Estimadores**
  - Algoritmo IRLS com estimadores robustos de Huber e Fair (`internal/reconciliation/robust/`).
- [ ] **Persistência & Rotas de API da Fase 6**
  - Expor solvers heurísticos na API REST e persistir os resultados de `drift_score` e limites `min`/`max` no banco de dados.
- [ ] **Conexão com Grafo de Workspace**
  - Conectar a sugestão de design ótimo de rede de sensores diretamente ao canvas do Workspace.

---

## 🛡️ Fase 7: Stress Testing, Data Fuzzing & Validação Empírica

- [ ] **Engine de Data Fuzzing**
  - Gerador sintético de ruídos, congelamento de sinal (frozen sensor), bias e desvios para validação de ground-truth.
- [ ] **Simulações de Monte Carlo (ISO GUM)**
  - Cálculo de intervalos de confiança em reconciliações usando incertezas de medição expandidas.
- [ ] **Sanity Checker Físico**
  - Validador termodinâmico para barrar soluções com valores fisicamente impossíveis (ex: massa negativa).
- [ ] **Framework de Benchmarking Científico**
  - Comparativo automático de precisão/recall entre Teste Global ($\chi^2$), GLR e modelo de ML.

---

## ⚙️ Tarefas Operacionais & Engenharia Complementar

- [ ] **Pipeline de Ingestão MQTT Live**: Consumir tags ao vivo via broker em produção.
- [ ] **Estratégia de Particionamento (Partition Pruning)**: Particionamento mensal de tabelas de histórico no PostgreSQL.
- [ ] **Exportador de Métricas Prometheus**: Rota `/metrics` nativa para observabilidade da saúde do solver.
