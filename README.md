# Backend Lab

> An advanced, hands-on backend learning path: notes, exercises, and production-grade projects covering APIs, databases, authentication, caching, testing, and deployment.

![License: MIT](https://img.shields.io/badge/license-MIT-blue.svg)
![Status](https://img.shields.io/badge/status-in%20progress-orange)
![PRs welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)

<!-- Add the CI badge once .github/workflows/ci.yml exists:
![CI](https://github.com/yashvardhansingh442-dev/backend-lab/actions/workflows/ci.yml/badge.svg)
-->

---

## Table of Contents

- [About](#about)
- [Who This Is For](#who-this-is-for)
- [How to Use This Repo](#how-to-use-this-repo)
- [Progress Dashboard](#progress-dashboard)
- [Featured Projects](#featured-projects)
- [Repository Structure](#repository-structure)
- [Tech Stack](#tech-stack)
- [Getting Started](#getting-started)
- [Learning Log](#learning-log)
- [Related Repositories](#related-repositories)
- [Contributing](#contributing)
- [License](#license)

---

## About

This repository is my public record of learning backend engineering in depth. It serves two purposes:

1. **Learning:** structured notes, runnable examples, and exercises for each topic, written in my own words.
2. **Showcase:** real services built with the concepts, each with API docs, architecture notes, tests, and a deployment.

The goal is to go beyond "how to write an endpoint" and understand how data, networks, and systems behave under real conditions: failures, load, and security threats.

## Who This Is For

- **Beginners to intermediate learners** who want an ordered path instead of scattered tutorials.
- **Developers moving into backend** from other fields.
- **Recruiters and collaborators** who want to see how I learn, design, and document systems.

## How to Use This Repo

1. Start at `docs/00-foundations` and work through the tracks **in order**.
2. In each topic folder, read the `README.md` first, then run the `examples/`.
3. Try the `exercises/` **before** looking at `solutions/`.
4. Build the matching project in `apps/` to apply what you learned.
5. Read `pitfalls.md` in each topic to avoid common mistakes.

> Tip: star or watch the repo to follow along as new topics are added.

---

## Progress Dashboard

Legend: ✅ complete | 🚧 in progress | ⬜ not started

| # | Track | Status |
|---|-------|--------|
| 00 | Foundations (HTTP, networking, OS, Linux and shell) | ⬜ |
| 01 | Language Deep Dive (Python: typing, async, concurrency) | ⬜ |
| 02 | Web Frameworks (FastAPI) | ⬜ |
| 03 | API Design (REST, validation, pagination, versioning) | ⬜ |
| 04 | Databases: SQL (PostgreSQL, indexing, transactions) | ⬜ |
| 05 | Databases: ORM and Migrations (SQLAlchemy, Alembic) | ⬜ |
| 06 | NoSQL and Search (Redis, MongoDB basics) | ⬜ |
| 07 | Authentication and Authorization (JWT, sessions, OAuth2, RBAC) | ⬜ |
| 08 | Caching and Performance | ⬜ |
| 09 | Background Jobs and Queues (Celery, message brokers) | ⬜ |
| 10 | Testing (pytest, integration, load tests) | ⬜ |
| 11 | Security (OWASP Top 10, secrets, rate limiting) | ⬜ |
| 12 | Architecture and System Design | ⬜ |
| 13 | DevOps (Docker, CI/CD, cloud deployment) | ⬜ |
| 14 | Observability (logging, metrics, tracing) | ⬜ |
| 15 | Advanced Topics (WebSockets, GraphQL, gRPC, microservices) | ⬜ |

See [ROADMAP.md](./ROADMAP.md) for detailed goals and dates.

---

## Featured Projects

| Project | Description | Skills Demonstrated | Demo |
|---------|-------------|---------------------|------|
| URL Shortener | Short links with analytics | REST design, PostgreSQL, Redis caching | _coming soon_ |
| Auth Service | Standalone login and token service | JWT, refresh tokens, RBAC, hashing | _coming soon_ |
| Blog API | CRUD API with users and comments | Relations, pagination, migrations | _coming soon_ |
| Task Queue Service | Background job processing | Celery, retries, idempotency | _coming soon_ |
| Realtime Chat Backend | Rooms and presence | WebSockets, pub/sub | _coming soon_ |
| E-commerce API | Products, cart, orders, payments (test mode) | Transactions, webhooks, inventory | _coming soon_ |
| Rate Limiter | Reusable limiting middleware | Algorithms, Redis, concurrency | _coming soon_ |
| Full-Stack Capstone | End-to-end system | Serves my `frontend-lab` capstone | _coming soon_ |

Each project has its own README with API documentation, setup steps, an architecture diagram, and an `ARCHITECTURE.md` explaining the decisions made.

---

## Repository Structure

```
backend-lab/
├── docs/          # Learning tracks: notes, examples, exercises, solutions
├── apps/          # Deployable showcase services
├── packages/      # Shared code: auth helpers, db utilities, common models
├── labs/          # Experiments: mini-framework, load tests, algorithm builds
├── infra/         # Docker, compose files, deployment configs
├── resources/     # Curated books, courses, and references
└── .github/       # CI workflows and templates
```

Every topic folder in `docs/` follows the same pattern:

```
topic-name/
├── README.md       # Concepts explained in my own words
├── examples/       # Small runnable demos
├── exercises/      # Practice problems
├── solutions/      # Worked answers
└── pitfalls.md     # Common mistakes and further reading
```

Every service in `apps/` follows this pattern:

```
service-name/
├── README.md           # Overview, setup, API summary
├── ARCHITECTURE.md     # Decisions and trade-offs
├── app/                # Source code
├── tests/              # Unit and integration tests
├── migrations/         # Database migrations
├── Dockerfile
├── docker-compose.yml
├── .env.example        # Required variables, never real secrets
└── pyproject.toml
```

---

## Tech Stack

| Area | Tools |
|------|-------|
| Language | Python 3.12+ |
| Framework | FastAPI, Pydantic |
| Databases | PostgreSQL, Redis, MongoDB |
| ORM and Migrations | SQLAlchemy, Alembic |
| Auth | JWT, OAuth2, passlib/argon2 |
| Background Jobs | Celery, RabbitMQ or Redis |
| Testing | pytest, httpx, Locust (load testing) |
| Tooling | uv or pip, Ruff, mypy, pre-commit |
| DevOps | Docker, GitHub Actions, Render or Railway |
| Observability | structlog, Prometheus, OpenTelemetry |

_This list reflects the end goal. Items are added as I reach each track. I may add Node.js tracks later for comparison._

---

## Getting Started

### Prerequisites

- Python 3.12 or later
- Docker and Docker Compose
- Git

### Setup

```bash
# Clone the repository
git clone https://github.com/yashvardhansingh442-dev/backend-lab.git
cd backend-lab

# Go into a project
cd apps/<service-name>

# Create and activate a virtual environment
python -m venv .venv
source .venv/bin/activate        # Windows: .venv\Scripts\activate

# Install dependencies
pip install -r requirements.txt

# Copy the example environment file and fill in values
cp .env.example .env

# Start dependencies (database, cache) and run the service
docker compose up -d
uvicorn app.main:app --reload
```

API docs are then available at `http://localhost:8000/docs`.

### Running Tests

```bash
pytest
ruff check .
mypy .
```

> Never commit real secrets. Only `.env.example` belongs in the repository.

---

## Learning Log

I keep a dated record of what I learned and built in [LEARNING_LOG.md](./LEARNING_LOG.md). It shows how the repo grows over time.

---

## Related Repositories

- **[Frontend Lab](https://github.com/yashvardhansingh442-dev/frontend-lab)**: the matching frontend learning path. Its full-stack capstone consumes the APIs built here.
- **LEETCODE_DSA**: data structures and algorithms practice.

---

## Contributing

Contributions are welcome, especially:

- Fixing errors or unclear explanations
- Suggesting topics or resources
- Reporting broken examples

Please read [CONTRIBUTING.md](./CONTRIBUTING.md) before opening a pull request.

---

## License

This project is licensed under the MIT License. See [LICENSE](./LICENSE) for details.

---

## Connect

- GitHub: [@yashvardhansingh442-dev](https://github.com/yashvardhansingh442-dev)

If this repo helps you learn, consider giving it a star.
