# 📐 Radare Architecture & System Design

Plataforma de reconciliação de dados industriais e validação estatística de balanços de massa e energia.

## Visão Geral da Arquitetura

```
radare/
├── apps/
│   └── webapp/       # Frontend React + TypeScript + Canvas de Grafos (Vite)
├── client-api/       # Especificações e coleções HTTP (Bruno)
├── database/         # Migrações SQL e scripts de inicialização (PostgreSQL + LogDB)
├── docs/             # Documentação técnica, planejamento de fases e TODO roadmap
│   ├── planning/     # Detalhamento de metodologia científica (Fases 1 a 7)
│   ├── ARCHITECTURE.md
│   └── TODO.md
├── internal/         # Backend em Go (API REST, Solvers Lagrange, Robustos, CUSUM)
├── docker-compose.yml
└── Makefile
```

## Componentes Principais

1. **Backend (Go)**: API REST, autenticação JWT, engine de reconciliação matricial (Lagrange, M-Estimadores Huber/Fair, CUSUM/EWMA) e workers de ingestão.
2. **Frontend (React)**: Interface visual interativa para modelagem de fluxogramas de processos industriais e acompanhamento de métricas em tempo real.
3. **Database Layer**: PostgreSQL para persistência de modelos/grafos + LogDB para auditoria e histórico de séries temporais.
