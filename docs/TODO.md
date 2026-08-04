# 📋 Radare Platform Roadmap & TODOs

Roadmap e lista de tarefas (TODOs) da plataforma de reconciliação de dados industriais **Radare**.

---

## 🧮 1. Algoritmos de Reconciliação & Estatística
- [ ] **Otimização por Multiplicadores de Lagrange em C++/Go**
  - Refinar o cálculo matricial de reconciliação de balanço de massa e energia para grandes redes industriais.
- [ ] **Detecção Automática de Erros Grosseiros (Gross Error Detection)**
  - Implementar testes de hipóteses estatísticas (Chi-Square e GLR) para identificação de sensores descalibrados.

---

## ⚙️ 2. Backend & Ingestão de Dados
- [ ] **Pipeline de Ingestão MQTT**
  - Consumir medições de tags industriais em tempo real via broker MQTT.
- [ ] **Integração com InfluxDB**
  - Persistir séries temporais de resultados reconciliados no InfluxDB.
- [ ] **Reconciliação Agendada (Scheduled Reconciliation)**
  - Executar o solver de reconciliação automaticamente em intervalos de tempo configuráveis.
- [ ] **Notificações via Webhook**
  - Disparar alertas via Webhook em caso de violação de balanço de massa/energia.
- [ ] **API de Busca e Filtro em Logs de Auditoria**
  - Implementar busca e filtragem avançada nos logs de histórico do sistema.

---

## 💻 3. Webapp & Frontend (React / Vite)
- [ ] **Atualizações de Gráficos em Tempo Real**
  - Integração via WebSocket para atualizar nós e fluxos da rede em tempo real.
- [ ] **Visualizador de Diffs de Versão de Workspace**
  - Comparar alterações entre versões de modelos de redes industriais.
- [ ] **Exportação de Resultados**
  - Permitir download dos dados reconciliados nos formatos CSV e Excel.
- [ ] **Layout Mobile Responsive**
  - Otimizar a interface para dispositivos móveis e tablets.

---

## 🗄️ 4. Banco de Dados & Infraestrutura
- [ ] **Estratégia de Particionamento (Partition Pruning)**
  - Implementar partição no PostgreSQL para histórico de reconciliações massivas.
- [ ] **Política de Retenção do LogDB**
  - Configurar limpeza e expiração automática de logs antigos.
- [ ] **Backups Automatizados & Monitoramento**
  - Script de backup automático do PostgreSQL em produção e endpoints de health check externos.
