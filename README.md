# Pokémon TCG Match Analytics API

A personal open-source REST API for recording and analyzing Pokémon TCG match data across tournaments and casual games. Part of a larger project that includes a [web app](#) and a [mobile app](#).

Built with FastAPI and PostgreSQL as a portfolio piece to apply backend development concepts through something I'm passionate about.

---

## Features

- **User registration & authentication** — secure access for each player
- **Deck management & versioning** — track how your decks evolve over time
- **Match recording** — log results from tournaments and casual games
- **Deck statistics** — win rates, performance trends, and more
- **Matchup analysis** — understand how your deck performs against specific archetypes
- **Card statistics** — evaluate the impact of individual cards across games
- **Opening hand analysis** — analyze your starting hand patterns and consistency

---

## Tech Stack

| Layer | Technology |
|---|---|
| Language | Python 3.12 |
| Framework | FastAPI |
| ORM | SQLAlchemy |
| Database | PostgreSQL |
| Cache | Redis |
| Data analysis | Pandas |
| Containerization | Docker & Docker Compose |
| CI/CD | GitHub Actions |

---

## Architecture

This project follows a **Clean Architecture / Ports & Adapters** pattern, keeping business logic decoupled from frameworks and infrastructure.

```
app/
├── api/               # HTTP layer — routes, request/response schemas
├── domain/            # Core business logic — entities, domain rules
├── application/       # Use cases — orchestrate domain and infrastructure
├── infrastructure/    # DB, cache, external services implementations
└── analytics/         # Data processing and statistics logic (Pandas)
```

---

## Getting Started

### Prerequisites

- [Docker](https://www.docker.com/) and Docker Compose
- [Python 3.12+](https://www.python.org/) (if running locally without Docker)

### Run with Docker (recommended)

```bash
# 1. Clone the repository
git clone https://github.com/MikeOwer/poketcg-analytics-api.git
cd poketcg-analytics-api

# 2. Copy the environment variables file and fill in your values
cp .env.example .env

# 3. Start all services
docker compose up --build
```

The API will be available at `http://localhost:8000`.  
Interactive docs: `http://localhost:8000/docs`

### Run locally

```bash
# 1. Create and activate a virtual environment
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate

# 2. Install dependencies
pip install -r requirements.txt

# 3. Copy the environment variables file and fill in your values
cp .env.example .env

# 4. Run database migrations
alembic upgrade head

# 5. Start the development server
uvicorn app.main:app --reload
```

---

## Roadmap

- [x] Project setup & architecture definition
- [ ] Docker & Docker Compose setup
- [ ] User registration & authentication (JWT)
- [ ] CI/CD pipeline with GitHub Actions
- [ ] Deck management & versioning
- [ ] Match recording endpoints
- [ ] Deck & matchup statistics
- [ ] Card statistics
- [ ] Opening hand analysis
- [ ] Web app integration
- [ ] Mobile app integration

---

## Related Repositories

| Repo | Description |
|---|---|
| [poketcg-analytics-web](#) | React web application |
| [poketcg-analytics-mobile](#) | React Native mobile application |
| [poketcg-analytics-hub](#) | Project overview & architecture docs |

---

## License

License TBD. See [LICENSE](./LICENSE) for details once defined.
