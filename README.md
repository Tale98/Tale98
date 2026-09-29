# Hi, I'm Apisit Chiamkhunthod 👋

**Full-Stack & DevOps Engineer** — Angular · .NET · Python · High-Availability Linux

5+ years building systems end to end and keeping them running. I work across Angular frontends, .NET and Python backends, PostgreSQL and Redis, and Linux infrastructure with Docker. My day job is a network simulation and topology platform, so I'm used to data-heavy workloads, background job queues, and systems that can't afford to go down. I design the architecture, build it, and set up failover so a single server failure doesn't take you offline.

🌐 Thai (native) · English (technical, written)

## Skills

| Area | Tools |
|---|---|
| Frontend | Angular 21, TypeScript, Angular Material, Tailwind CSS, Chart.js, RxJS |
| Backend · .NET | C# / .NET 10, Dapper, Npgsql, StackExchange.Redis, LINQ |
| Backend · Python | FastAPI, SQLModel / SQLAlchemy, Alembic, Django, Celery, pandas, paramiko |
| Data stores | PostgreSQL, Redis, SQLite |
| Infrastructure & HA | Linux, Docker, Docker Compose, nginx, keepalived (VIP), PostgreSQL streaming replication, WAL archiving |
| Auth & access | JWT, RBAC |
| Visualization | Plotly Dash, Plotly.NET, ScottPlot |
| Networks & graphs | Topology processing, router config parsing, QuikGraph, Suurballe (disjoint paths) |

## Featured project

### IPAM: IP Address Management platform (design & build)

Sole developer. Designed and built the full stack, including a high-availability deployment where one server failing doesn't take the service down.

```
Frontend x2 (keepalived VIP)   Angular 21 SPA on nginx
        │  TCP 443
Backend x2  (keepalived VIP)   nginx reverse proxy → FastAPI (internal :8000)
        │  TCP 5432
Database x2                    PostgreSQL 18 main → replica
```

- Full stack: Angular 21 (Material, Tailwind CSS, Chart.js), FastAPI with SQLModel and Alembic migrations, PostgreSQL 18
- Six-server layout with Docker Compose (2 frontend, 2 backend, 2 database), with the API reachable only through the reverse proxy
- keepalived virtual IPs for automatic failover on both the frontend and backend tiers
- PostgreSQL main/replica streaming replication with `pg_basebackup` and WAL archiving, plus a controlled manual promotion procedure
- Core IPAM features for managing IP addresses and subnets
- Role-based access (admin, operator) with hierarchical groups, join requests approved by group admins, and membership transfers

### Public demo of the same design: [fullstack-ha-demo](https://github.com/Tale98/fullstack-ha-demo)

A generic, runnable Docker Compose lab of the HA layout above: keepalived failover for frontend and backend, PostgreSQL replica with a shared WAL archive, JWT in an HttpOnly cookie, TLS on every hop. Includes failover drills and a probe tool to watch them live.

## Experience

**Developer — network simulation & topology software** · current, 5+ years

- Built a .NET 10 background service (Dapper, Npgsql, StackExchange.Redis) that processes jobs from multiple Redis queues, with separate slow and fast worker pools configured per deployment
- Integrated it into an existing FastAPI + Celery + Redis + PostgreSQL stack so Python and .NET services share one job pipeline
- Migrated a Python data pipeline (pandas, paramiko, regex) that parses router configs and topology into C# with LINQ, Dapper and QuikGraph
- Worked with graph algorithms for network resilience, including Suurballe's algorithm for disjoint paths
- Troubleshot simulations on Linux VMs, including I/O slowdowns caused by runaway log files
- Built interactive dashboards with Django + Plotly Dash, and charts in C# with ScottPlot and Plotly.NET
- Debugged containerized environments (Docker, PostgreSQL, MLflow) and wrote bulk-insert routines from pandas into PostgreSQL

## Get in touch

- Email: [apisit.chaimkhunthod@gmail.com](mailto:apisit.chaimkhunthod@gmail.com)
- LinkedIn: [apisit-chiamkhunthod](https://www.linkedin.com/in/apisit-chiamkhunthod-2a11221b4/)
