# radare

Industrial data reconciliation platform using Lagrange Multipliers and chi-squared validation for mass and energy balance integrity.

## Architecture

```
apps/
  backend/            Go API and reconciliation engine (Port 8080)
  webapp/             React SPA (Port 5173 dev / 80 prod)
database/
  coredb_migrations/  Core database SQL migrations
  logdb_migrations/   Audit log database SQL migrations
  coredb_seeds/       Initial seed data
  cmd/migrate/        Database migration CLI
client-api/           Bruno API collection
.gitea/workflows/     CI/CD pipeline definitions
```

### Components

- `apps/backend`: Go backend utilizing GORM and `gonum` for mathematical optimization and balance solving.
- `apps/webapp`: React frontend built with Vite, TanStack Router/Query, and React Flow.

### Reconciliation Engine

Process nodes contain measured streams and tags. The reconciliation algorithm applies Lagrange Multipliers to minimize weighted squared deviations while satisfying conservation constraints. Statistical integrity is evaluated via $\chi^2$ hypothesis testing.

## Development

### Prerequisites

- Go 1.25+
- Node.js 20+
- Docker / Podman

### Running Services

Initialize databases, run migrations, and apply seeds:

```bash
make db-bootstrap
```

Start full development environment:

```bash
make dev
```

### Database Management

```bash
make migrate        # Run coredb migrations
make seed           # Apply coredb seeds
make migrate-log    # Run logdb migrations
make seed-log       # Apply logdb seeds
make nuke-and-pave  # Reset database volumes and reapply migrations
```

### Service Endpoints

| Service | Type | Port | Endpoint |
|---------|------|------|----------|
| Web App | Frontend | `5173` | http://localhost:5173 |
| HTTP API | Backend | `8080` | http://localhost:8080 |
| PostgreSQL Core | Database | `5432` | localhost:5432/radare |
| PostgreSQL Logs | Database | `5433` | localhost:5433/radare_logs |
| Redis | Cache | `6379` | localhost:6379 |


## Documentation

- [📋 Roadmap & TODOs](docs/TODO.md) - Planned features and project roadmap
- [📐 Architecture](docs/ARCHITECTURE.md) - System architecture and components
- [📄 License](LICENSE) - MIT License
