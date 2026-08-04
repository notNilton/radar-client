# 📋 Radare Platform Roadmap & TODOs

Roadmap e planejamento de tarefas para a plataforma **Radare** (Reconciliação de Dados Industriais e Validação Estatística).

---

## 🧮 1. Algoritmos de Reconciliação & Estatística Avançada (Fase 6 & 7)
- [x] **Genetic Algorithm & M-Estimadores Robustos**
  - Implementados em `internal/reconciliation/` (Huber, Fair, Solver Genético).
- [ ] **Exposição das APIS de Solvers Avançados**
  - Criar endpoints REST para permitir escolha entre o Solver de Lagrange e o Solver Genético / M-Estimadores.
- [ ] **Persistência de Métricas de Drift (CUSUM / EWMA)**
  - Salvar histórico de detecção de drift no LogDB e notificar desvios em tempo real.
- [ ] **Data Fuzzing & Simulação Monte Carlo (ISO GUM)**
  - Motor de injeção de erros sintéticos e cálculo de intervalo de confiança para validação empírica.

---

## ⚙️ 2. Backend & Ingestão de Dados
- [ ] **Pipeline de Ingestão MQTT Live**
  - Consumir medições de tags industriais ao vivo via broker em produção.
- [ ] **Integração Time-Series com InfluxDB**
  - Persistir histórico de séries temporais reconciliadas.
- [ ] **Exportador de Métricas Prometheus**
  - Endpoint `/metrics` nativo para observabilidade do sistema e saúde dos solvers.

---

## 💻 3. Webapp & Interface (React / Vite)
- [ ] **Visualização de Diffs de Topologia de Grafo**
  - Interface para comparar alterações entre versões de modelos da fábrica.
- [ ] **Exportação de Relatórios Executive (CSV / Excel / PDF)**
  - Download de balanços de massa e energia reconciliados.

---

## 🗄️ 4. Banco de Dados & Infraestrutura
- [ ] **Particionamento Mensal no PostgreSQL (Partition Pruning)**
  - Estratégia de particionamento da tabela de histórico de reconciliações.
- [ ] **Pipelines de CI/CD via GitHub Actions**
  - Automação de testes em Go, Vitest e validação de builds do Docker.
