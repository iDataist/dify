# Cascade Chat Conversation

  Note: _This is purely the output of the chat conversation and does not contain any raw data, codebase snippets, etc. used to generate the output._

### User Input

Walk me through the architecture of this repo

*Updated todo list*

### Planner Response

I’ll scan the repository structure to ground the walkthrough in the actual code. First, I’ll list the root directory to identify key folders and files.

*Listed directory [dify](file:///Users/hren/Downloads/dify) *

### Planner Response

I’ll scan key directories and docs to ground the architecture overview in the actual codebase. I’ll list major folders and read the top-level README to capture any described architecture. Then I’ll peek into [api/](cci:7://file:///Users/hren/Downloads/dify/api:0:0-0:0), [web/](cci:7://file:///Users/hren/Downloads/dify/web:0:0-0:0), [docker/](cci:7://file:///Users/hren/Downloads/dify/docker:0:0-0:0), [dev/](cci:7://file:///Users/hren/Downloads/dify/dev:0:0-0:0), [scripts/](cci:7://file:///Users/hren/Downloads/dify/scripts:0:0-0:0), [sdks/](cci:7://file:///Users/hren/Downloads/dify/sdks:0:0-0:0), and [docs/](cci:7://file:///Users/hren/Downloads/dify/docs:0:0-0:0) to summarize structure. I’ll run these lookups in parallel.

*Viewed [README.md](file:///Users/hren/Downloads/dify/README.md) *

*Viewed [Makefile](file:///Users/hren/Downloads/dify/Makefile) *

*Listed directory [api](file:///Users/hren/Downloads/dify/api) *

*Listed directory [web](file:///Users/hren/Downloads/dify/web) *

*Listed directory [docker](file:///Users/hren/Downloads/dify/docker) *

*Listed directory [dev](file:///Users/hren/Downloads/dify/dev) *

*Listed directory [scripts](file:///Users/hren/Downloads/dify/scripts) *

*Listed directory [sdks](file:///Users/hren/Downloads/dify/sdks) *

*Listed directory [docs](file:///Users/hren/Downloads/dify/docs) *

*Viewed [README.md](file:///Users/hren/Downloads/dify/api/README.md) *

### Planner Response

I’ll inspect key backend, frontend, and deployment files to describe the concrete architecture and data flow. I’ll open representative files and list key directories in parallel for speed.

*Viewed [app_factory.py](file:///Users/hren/Downloads/dify/api/app_factory.py) *

*Viewed [app.py](file:///Users/hren/Downloads/dify/api/app.py) *

*Viewed [pyproject.toml](file:///Users/hren/Downloads/dify/api/pyproject.toml) *

*Listed directory [core](file:///Users/hren/Downloads/dify/api/core) *

*Listed directory [controllers](file:///Users/hren/Downloads/dify/api/controllers) *

*Listed directory [services](file:///Users/hren/Downloads/dify/api/services) *

*Listed directory [models](file:///Users/hren/Downloads/dify/api/models) *

*Listed directory [repositories](file:///Users/hren/Downloads/dify/api/repositories) *

*Viewed [README.md](file:///Users/hren/Downloads/dify/web/README.md) *

*Viewed [package.json](file:///Users/hren/Downloads/dify/web/package.json) *

*Viewed [next.config.js](file:///Users/hren/Downloads/dify/web/next.config.js) *

*Viewed [middleware.ts](file:///Users/hren/Downloads/dify/web/middleware.ts) *

*Listed directory [app](file:///Users/hren/Downloads/dify/web/app) *

*Listed directory [service](file:///Users/hren/Downloads/dify/web/service) *

*Listed directory [nginx](file:///Users/hren/Downloads/dify/docker/nginx) *

*Viewed [docker-compose.yaml](file:///Users/hren/Downloads/dify/docker/docker-compose.yaml) *

*Viewed [README.md](file:///Users/hren/Downloads/dify/docker/README.md) *

### Planner Response

To confirm how API routes are wired, I'll open `api/extensions/ext_blueprints.py` to see how blueprints are registered and which controller modules get included.

*Searched filesystem*

*Viewed [ext_blueprints.py](file:///Users/hren/Downloads/dify/api/extensions/ext_blueprints.py) *

*Viewed [dify_app.py](file:///Users/hren/Downloads/dify/api/dify_app.py) *

*Grep searched codebase*

*Listed directory [tasks](file:///Users/hren/Downloads/dify/api/tasks) *

*Listed directory [schedule](file:///Users/hren/Downloads/dify/api/schedule) *

*Updated todo list*

### Planner Response

# Repo Architecture Overview

I grounded this walkthrough in the actual code by inspecting [README.md](cci:7://file:///Users/hren/Downloads/dify/README.md:0:0-0:0), [Makefile](cci:7://file:///Users/hren/Downloads/dify/Makefile:0:0-0:0), [api/](cci:7://file:///Users/hren/Downloads/dify/api:0:0-0:0), [web/](cci:7://file:///Users/hren/Downloads/dify/web:0:0-0:0), [docker/](cci:7://file:///Users/hren/Downloads/dify/docker:0:0-0:0), and key files like [api/app_factory.py](cci:7://file:///Users/hren/Downloads/dify/api/app_factory.py:0:0-0:0), [api/extensions/ext_blueprints.py](cci:7://file:///Users/hren/Downloads/dify/api/extensions/ext_blueprints.py:0:0-0:0), [web/package.json](cci:7://file:///Users/hren/Downloads/dify/web/package.json:0:0-0:0), and [docker/docker-compose.yaml](cci:7://file:///Users/hren/Downloads/dify/docker/docker-compose.yaml:0:0-0:0). I also followed the conventions in the [AGENTS.md](cci:7://file:///Users/hren/Downloads/dify/AGENTS.md:0:0-0:0) memory for workflows and quality checks.

# Top-level Structure

- **[api/](cci:7://file:///Users/hren/Downloads/dify/api:0:0-0:0)**: Flask backend (DDD/Clean Architecture), Celery workers, RAG/Workflow engines.
- **[web/](cci:7://file:///Users/hren/Downloads/dify/web:0:0-0:0)**: Next.js 15 + React 19 frontend, PWA, Storybook, i18n.
- **[docker/](cci:7://file:///Users/hren/Downloads/dify/docker:0:0-0:0)**: Compose stacks, middleware profiles, Nginx, certbot, SSRF proxy, vector DBs.
- **[dev/](cci:7://file:///Users/hren/Downloads/dify/dev:0:0-0:0)**: Local dev helpers (type-check, pytest, start scripts).
- **[sdks/](cci:7://file:///Users/hren/Downloads/dify/sdks:0:0-0:0)**: Thin clients for Python/Node/PHP.
- **[Makefile](cci:7://file:///Users/hren/Downloads/dify/Makefile:0:0-0:0)**: One-liners for init, lint, type-check, docker build.
- **[docs/](cci:7://file:///Users/hren/Downloads/dify/docs:0:0-0:0)**: Localized docs.

# Backend ([api/](cci:7://file:///Users/hren/Downloads/dify/api:0:0-0:0)) Architecture

- **App factory & lifecycle**
  - [app_factory.create_app()](cci:1://file:///Users/hren/Downloads/dify/api/app_factory.py:33:0-40:14) builds [DifyApp](cci:2://file:///Users/hren/Downloads/dify/api/dify_app.py:3:0-4:8) with config from `.env` via `configs.dify_config` and initializes extensions in [initialize_extensions()](cci:1://file:///Users/hren/Downloads/dify/api/app_factory.py:43:0-107:98) using `ext_*` modules.
    - File: [api/app_factory.py](cci:7://file:///Users/hren/Downloads/dify/api/app_factory.py:0:0-0:0)
    - App type: [api/dify_app.py](cci:7://file:///Users/hren/Downloads/dify/api/dify_app.py:0:0-0:0) ([DifyApp(Flask)](cci:2://file:///Users/hren/Downloads/dify/api/dify_app.py:3:0-4:8))
  - [api/app.py](cci:7://file:///Users/hren/Downloads/dify/api/app.py:0:0-0:0) selects a migrations-only app for `flask db` vs full app for serving and exposes `celery` via `app.extensions["celery"]`.

- **Extensions & cross-cutting concerns**
  - Registered in [initialize_extensions()](cci:1://file:///Users/hren/Downloads/dify/api/app_factory.py:43:0-107:98):
    - Logging, warnings, JSON (`ext_logging`, `ext_orjson`)
    - DB & migrations (`ext_database`, `ext_migrate`) → SQLAlchemy models under [api/models/](cci:7://file:///Users/hren/Downloads/dify/api/models:0:0-0:0)
    - Celery (`ext_celery`) → tasks in [api/tasks/](cci:7://file:///Users/hren/Downloads/dify/api/tasks:0:0-0:0), periodic in [api/schedule/](cci:7://file:///Users/hren/Downloads/dify/api/schedule:0:0-0:0)
    - Redis (`ext_redis`)
    - Storage abstraction (`ext_storage`) → local/opendal/S3/Azure/GCS
    - SSO/login (`ext_login`), mail (`ext_mail`)
    - Observability: Sentry (`ext_sentry`), OTEL (`ext_otel`), app metrics (`ext_app_metrics`), request logging (`ext_request_logging`)
    - Reverse proxy headers (`ext_proxy_fix`), timezone, hosting provider adapter
    - Blueprint registration (`ext_blueprints`)
  - File: [api/app_factory.py](cci:7://file:///Users/hren/Downloads/dify/api/app_factory.py:0:0-0:0) lines 44–95

- **Routing layer (Blueprints)**
  - [api/extensions/ext_blueprints.py](cci:7://file:///Users/hren/Downloads/dify/api/extensions/ext_blueprints.py:0:0-0:0) registers:
    - `controllers.service_api` (service APIs for apps)
    - `controllers.web` (web console APIs)
    - `controllers.console` (admin/console)
    - `controllers.files` (file upload/serve)
    - `controllers.inner_api` (internal)
    - `controllers.mcp` (Model Context Protocol)
  - CORS configured per blueprint using `dify_config.*CORS_ALLOW_ORIGINS`.

- **Domain & application layers**
  - Controllers (HTTP) → Services (business logic) → Models/Repositories:
    - Controllers: `api/controllers/*`
    - Services: `api/services/*` (e.g., [dataset_service.py](cci:7://file:///Users/hren/Downloads/dify/api/services/dataset_service.py:0:0-0:0), [workflow_service.py](cci:7://file:///Users/hren/Downloads/dify/api/services/workflow_service.py:0:0-0:0), [model_provider_service.py](cci:7://file:///Users/hren/Downloads/dify/api/services/model_provider_service.py:0:0-0:0))
    - Models: `api/models/*` (SQLAlchemy entities)
    - Repos: `api/repositories/*` and `api/core/repositories/*`
  - “Core” domain (engines and providers):
    - [api/core/workflow/](cci:7://file:///Users/hren/Downloads/dify/api/core/workflow:0:0-0:0) Graph engine, execution, nodes, repositories
    - [api/core/rag/](cci:7://file:///Users/hren/Downloads/dify/api/core/rag:0:0-0:0) Ingestion, chunking, retrievers, vector stores
    - [api/core/model_runtime/](cci:7://file:///Users/hren/Downloads/dify/api/core/model_runtime:0:0-0:0) Provider integrations (OpenAI, Bedrock, etc.)
    - [api/core/tools/](cci:7://file:///Users/hren/Downloads/dify/api/core/tools:0:0-0:0) Built-in agent tools, [api/core/agent/](cci:7://file:///Users/hren/Downloads/dify/api/core/agent:0:0-0:0)
    - [api/core/provider_manager.py](cci:7://file:///Users/hren/Downloads/dify/api/core/provider_manager.py:0:0-0:0), [api/core/model_manager.py](cci:7://file:///Users/hren/Downloads/dify/api/core/model_manager.py:0:0-0:0)

- **Background processing**
  - Celery tasks: [api/tasks/](cci:7://file:///Users/hren/Downloads/dify/api/tasks:0:0-0:0) (e.g., document indexing, dataset maintenance, email jobs, workflow execution offloading)
  - Schedules (beat): [api/schedule/](cci:7://file:///Users/hren/Downloads/dify/api/schedule:0:0-0:0) (e.g., cleanup, queue monitoring)
  - Worker entrypoint: [api/celery_entrypoint.py](cci:7://file:///Users/hren/Downloads/dify/api/celery_entrypoint.py:0:0-0:0)

- **Config & quality**
  - Config: `.env` → [api/configs/](cci:7://file:///Users/hren/Downloads/dify/api/configs:0:0-0:0) (Pydantic settings)
  - Lint/type/test:
    - `make lint` runs ruff + import lints
    - `make type-check` runs basedpyright
    - Tests with `uv run pytest` using [api/pytest.ini](cci:7://file:///Users/hren/Downloads/dify/api/pytest.ini:0:0-0:0), [api/tests/](cci:7://file:///Users/hren/Downloads/dify/api/tests:0:0-0:0)
  - Dependencies: [api/pyproject.toml](cci:7://file:///Users/hren/Downloads/dify/api/pyproject.toml:0:0-0:0) with groups for dev/storage/tools/vdb.

# Frontend ([web/](cci:7://file:///Users/hren/Downloads/dify/web:0:0-0:0)) Architecture

- **Framework & build**
  - Next.js 15 (App Router) + React 19. PWA via `next-pwa`, MDX support, bundle analyzer.
  - Scripts: `pnpm dev`, `pnpm build`, `pnpm start`, lint/test (`eslint`, `jest`).
  - Files: [web/package.json](cci:7://file:///Users/hren/Downloads/dify/web/package.json:0:0-0:0), [web/next.config.js](cci:7://file:///Users/hren/Downloads/dify/web/next.config.js:0:0-0:0), [web/README.md](cci:7://file:///Users/hren/Downloads/dify/web/README.md:0:0-0:0).

- **App structure**
  - [web/app/](cci:7://file:///Users/hren/Downloads/dify/web/app:0:0-0:0) App Router pages/layouts, many feature routes (`/apps`, [/install](cci:7://file:///Users/hren/Downloads/dify/web/app/install:0:0-0:0), [/signin](cci:7://file:///Users/hren/Downloads/dify/web/app/signin:0:0-0:0), etc.).
  - [web/service/](cci:7://file:///Users/hren/Downloads/dify/web/service:0:0-0:0) API client hooks and modules (e.g., [apps.ts](cci:7://file:///Users/hren/Downloads/dify/web/service/apps.ts:0:0-0:0), [datasets.ts](cci:7://file:///Users/hren/Downloads/dify/web/service/datasets.ts:0:0-0:0), [use-workflow.ts](cci:7://file:///Users/hren/Downloads/dify/web/service/use-workflow.ts:0:0-0:0)).
  - [web/i18n/](cci:7://file:///Users/hren/Downloads/dify/web/i18n:0:0-0:0) and [web/i18n-config/](cci:7://file:///Users/hren/Downloads/dify/web/i18n-config:0:0-0:0) for localization.
  - [web/middleware.ts](cci:7://file:///Users/hren/Downloads/dify/web/middleware.ts:0:0-0:0) sets CSP and `X-Frame-Options` with `NEXT_PUBLIC_CSP_WHITELIST`.
  - State & data:
    - React Query (`@tanstack/react-query`)
    - Zustand (`zustand`), hooks in [web/service/](cci:7://file:///Users/hren/Downloads/dify/web/service:0:0-0:0) and [web/context/](cci:7://file:///Users/hren/Downloads/dify/web/context:0:0-0:0)
  - UI: Tailwind, shadcn-style primitives, Storybook in [.storybook/](cci:7://file:///Users/hren/Downloads/dify/web/.storybook:0:0-0:0), components in [web/app/components/](cci:7://file:///Users/hren/Downloads/dify/web/app/components:0:0-0:0).

- **Integration points**
  - Env expects API prefixes:
    - `NEXT_PUBLIC_API_PREFIX` → `http://localhost:5001/console/api`
    - `NEXT_PUBLIC_PUBLIC_API_PREFIX` → `http://localhost:5001/api`
  - Image host allowlist computed in [next.config.js](cci:7://file:///Users/hren/Downloads/dify/web/next.config.js:0:0-0:0).

# Deployment ([docker/](cci:7://file:///Users/hren/Downloads/dify/docker:0:0-0:0)) Architecture

- **Compose stacks**
  - [docker/docker-compose.yaml](cci:7://file:///Users/hren/Downloads/dify/docker/docker-compose.yaml:0:0-0:0): Generated; includes:
    - [web](cci:7://file:///Users/hren/Downloads/dify/web:0:0-0:0), [api](cci:7://file:///Users/hren/Downloads/dify/api:0:0-0:0), `worker`, [nginx](cci:7://file:///Users/hren/Downloads/dify/docker/nginx:0:0-0:0), storage backends, DB (`db`), cache (`redis`), SSRF proxy, vector stores (Weaviate/Qdrant/Milvus/etc.), plugin daemon, optional OTEL collector.
  - [docker/docker-compose.middleware.yaml](cci:7://file:///Users/hren/Downloads/dify/docker/docker-compose.middleware.yaml:0:0-0:0): Middleware-only for local dev.
  - Nginx config templates under [docker/nginx/](cci:7://file:///Users/hren/Downloads/dify/docker/nginx:0:0-0:0).

- **Configuration**
  - [.env.example](cci:7://file:///Users/hren/Downloads/dify/web/.env.example:0:0-0:0) is extensive; you must `cp` to `.env` and adjust.
  - Vector DB selectable with `VECTOR_STORE`.
  - URLs: `CONSOLE_*`, `SERVICE_API_URL`, `APP_API_URL`, `APP_WEB_URL`, `FILES_URL`.
  - Security/observability: Sentry, OTEL, CSP.

- **Local dev helpers**
  - `make dev-setup`: spins middleware + prepares web and api envs.
  - [dev/start-api](cci:7://file:///Users/hren/Downloads/dify/dev/start-api:0:0-0:0), [dev/start-worker](cci:7://file:///Users/hren/Downloads/dify/dev/start-worker:0:0-0:0) can run backend services locally.

# End-to-end Data Flow

```mermaid
flowchart LR
  Browser -->|HTTP(S)| Nginx["docker/nginx"]
  Nginx -->|/console/*| Web["web (Next.js)"]
  Nginx -->|/api/*| API["api (Flask/Gunicorn)"]

  subgraph Backend
    API --> Blueprints["ext_blueprints → controllers.service_api/web/console/files/inner_api/mcp"]
    Blueprints --> Services["api/services/*"]
    Services --> Models["api/models/* (SQLAlchemy)"]
    Services --> Core["api/core/* (workflow, rag, model_runtime, tools)"]
    Services --> Storage["S3/Azure/GCS/local via ext_storage"]
    Services --> VDB["Vector DB (Weaviate/Qdrant/Milvus/...)"]
    Services --> Redis["Redis (cache, Celery broker)"]
    Services -->|async jobs| Celery["api/tasks/* (workers)"]
    Celery --> VDB
    Celery --> Storage
    Celery --> Models
  end

  Web -->|REST/Fetch| Nginx
```

# Typical Request Lifecycle

- **Frontend** calls `${NEXT_PUBLIC_API_PREFIX}` or `${NEXT_PUBLIC_PUBLIC_API_PREFIX}` from `web/service/*`.
- **Nginx** routes to [api](cci:7://file:///Users/hren/Downloads/dify/api:0:0-0:0) or [web](cci:7://file:///Users/hren/Downloads/dify/web:0:0-0:0) containers.
- **Flask** routes via blueprints in [api/extensions/ext_blueprints.py](cci:7://file:///Users/hren/Downloads/dify/api/extensions/ext_blueprints.py:0:0-0:0).
- **Controller** in `api/controllers/...` coordinates a `..._service.py`.
- **Service** uses:
  - Domain engines in [api/core/](cci:7://file:///Users/hren/Downloads/dify/api/core:0:0-0:0) (workflow execution, RAG ingestion/retrieval, provider calls).
  - Models in [api/models/](cci:7://file:///Users/hren/Downloads/dify/api/models:0:0-0:0) via SQLAlchemy.
  - Celery for long-running tasks in [api/tasks/](cci:7://file:///Users/hren/Downloads/dify/api/tasks:0:0-0:0).
  - Vector DB + object storage via configured clients.

# Developer Workflow (from repo)

- **Backend**
  - Setup: `make dev-setup` or manual per [api/README.md](cci:7://file:///Users/hren/Downloads/dify/api/README.md:0:0-0:0).
  - Migrate: `uv run flask db upgrade`.
  - Run API: `uv run flask run --host 0.0.0.0 --port=5001 --debug`.
  - Run worker: `uv run celery -A app.celery worker ...`.
  - Quality: `make lint`, `make type-check`, `uv run pytest`.

- **Frontend**
  - Setup: `pnpm install`, copy [.env.example](cci:7://file:///Users/hren/Downloads/dify/web/.env.example:0:0-0:0) → `.env.local`, set `NEXT_PUBLIC_*` prefixes.
  - Run: `pnpm dev`.
  - Lint/tests: `pnpm lint`, `pnpm test`.

- **Docker**
  - Quick start: `cd docker && cp .env.example .env && docker compose up -d`.
  - Middleware-only for dev: `docker compose -f docker-compose.middleware.yaml --profile weaviate -p dify up -d`.

# Where to Add or Change Things

- **New API endpoint**: `api/controllers/<area>/...`, wire via blueprint, add service in `api/services/...`, models/migrations in [api/models/](cci:7://file:///Users/hren/Downloads/dify/api/models:0:0-0:0) + `flask db migrate/upgrade`.
- **New workflow node/feature**: `api/core/workflow/nodes/` and relevant repos/services.
- **New tool/provider**: [api/core/tools/](cci:7://file:///Users/hren/Downloads/dify/api/core/tools:0:0-0:0) or [api/core/model_runtime/](cci:7://file:///Users/hren/Downloads/dify/api/core/model_runtime:0:0-0:0) and register in [provider_manager.py](cci:7://file:///Users/hren/Downloads/dify/api/core/provider_manager.py:0:0-0:0).
- **Frontend feature/page**: `web/app/<route>/...`, data fetch in `web/service/...`, strings in `web/i18n/en-US/`.

# Notable Files and Paths

- **App**: [api/app_factory.py](cci:7://file:///Users/hren/Downloads/dify/api/app_factory.py:0:0-0:0), [api/app.py](cci:7://file:///Users/hren/Downloads/dify/api/app.py:0:0-0:0)
- **Blueprints**: [api/extensions/ext_blueprints.py](cci:7://file:///Users/hren/Downloads/dify/api/extensions/ext_blueprints.py:0:0-0:0)
- **Domain**: [api/core/workflow/](cci:7://file:///Users/hren/Downloads/dify/api/core/workflow:0:0-0:0), [api/core/rag/](cci:7://file:///Users/hren/Downloads/dify/api/core/rag:0:0-0:0), [api/core/model_runtime/](cci:7://file:///Users/hren/Downloads/dify/api/core/model_runtime:0:0-0:0), [api/core/tools/](cci:7://file:///Users/hren/Downloads/dify/api/core/tools:0:0-0:0)
- **Services**: `api/services/*`
- **Models**: `api/models/*`
- **Tasks**: `api/tasks/*`, schedules in `api/schedule/*`
- **Frontend**: [web/app/](cci:7://file:///Users/hren/Downloads/dify/web/app:0:0-0:0), [web/service/](cci:7://file:///Users/hren/Downloads/dify/web/service:0:0-0:0), [web/middleware.ts](cci:7://file:///Users/hren/Downloads/dify/web/middleware.ts:0:0-0:0), [web/i18n/](cci:7://file:///Users/hren/Downloads/dify/web/i18n:0:0-0:0)
- **Compose**: [docker/docker-compose.yaml](cci:7://file:///Users/hren/Downloads/dify/docker/docker-compose.yaml:0:0-0:0), `docker/nginx/*`

# Summary

- **Backend**: Flask app with clear layering (controllers → services → models/core) and rich domain engines for workflow/RAG; Celery for background jobs; configurable via `.env`.
- **Frontend**: Next.js App Router + React 19 with PWA, i18n, and typed API service modules.
- **Deployment**: Docker Compose with Nginx, Postgres, Redis, optional vector DBs and observability; local middleware profile for dev.
- I followed the development and quality checks described in [AGENTS.md](cci:7://file:///Users/hren/Downloads/dify/AGENTS.md:0:0-0:0) to frame commands and architecture boundaries.

If you want, I can dive into a specific path (e.g., workflow execution in [api/core/workflow/](cci:7://file:///Users/hren/Downloads/dify/api/core/workflow:0:0-0:0) or how file ingestion flows through [api/services/dataset_service.py](cci:7://file:///Users/hren/Downloads/dify/api/services/dataset_service.py:0:0-0:0)) and trace a request end-to-end.

### User Input

What is the main use case for dify? What is the value it provides?

*Updated todo list*

### Planner Response

# Main Use Case

- **Build production-grade LLM apps quickly**  
  Create chatbots, agents, and RAG knowledge apps with a visual workflow builder and ship them as APIs or UIs.  
  - Workflows: [api/core/workflow/](cci:7://file:///Users/hren/Downloads/dify/api/core/workflow:0:0-0:0) (graph engine, nodes, execution)  
  - Agents/tools: [api/core/agent/](cci:7://file:///Users/hren/Downloads/dify/api/core/agent:0:0-0:0), [api/core/tools/](cci:7://file:///Users/hren/Downloads/dify/api/core/tools:0:0-0:0)  
  - RAG: [api/core/rag/](cci:7://file:///Users/hren/Downloads/dify/api/core/rag:0:0-0:0) (ingestion, chunking, retrievers, vector stores)  
  - Backend APIs: [api/controllers/service_api/](cci:7://file:///Users/hren/Downloads/dify/api/controllers/service_api:0:0-0:0), [api/controllers/web/](cci:7://file:///Users/hren/Downloads/dify/api/controllers/web:0:0-0:0), [api/controllers/console/](cci:7://file:///Users/hren/Downloads/dify/api/controllers/console:0:0-0:0)  
  - Frontend console/UI: [web/app/](cci:7://file:///Users/hren/Downloads/dify/web/app:0:0-0:0), [web/service/](cci:7://file:///Users/hren/Downloads/dify/web/service:0:0-0:0)

# Value Provided

- **Speed from prototype to production**  
  Visual workflows + out-of-box REST APIs mean you skip boilerplate and wire-ups.  
  - App factory and blueprints: [api/app_factory.py](cci:7://file:///Users/hren/Downloads/dify/api/app_factory.py:0:0-0:0), [api/extensions/ext_blueprints.py](cci:7://file:///Users/hren/Downloads/dify/api/extensions/ext_blueprints.py:0:0-0:0)  
  - Ready endpoints for console/service/app: `api/controllers/*`  
  - Frontend scaffolding and PWA: [web/next.config.js](cci:7://file:///Users/hren/Downloads/dify/web/next.config.js:0:0-0:0), [web/app/](cci:7://file:///Users/hren/Downloads/dify/web/app:0:0-0:0)

- **Comprehensive model and tool ecosystem**  
  Integrate many LLMs and tools without custom glue.  
  - Model providers and orchestration: [api/core/model_runtime/](cci:7://file:///Users/hren/Downloads/dify/api/core/model_runtime:0:0-0:0), [api/core/provider_manager.py](cci:7://file:///Users/hren/Downloads/dify/api/core/provider_manager.py:0:0-0:0), [api/services/model_load_balancing_service.py](cci:7://file:///Users/hren/Downloads/dify/api/services/model_load_balancing_service.py:0:0-0:0)  
  - 50+ built-in tools and extensibility: [api/core/tools/](cci:7://file:///Users/hren/Downloads/dify/api/core/tools:0:0-0:0), `api/services/plugins/`

- **First-class RAG pipeline**  
  Ingest, index, retrieve, and ground responses with built-in vector DB integrations.  
  - Vector stores: [api/pyproject.toml](cci:7://file:///Users/hren/Downloads/dify/api/pyproject.toml:0:0-0:0) vdb group; compose services for Weaviate/Qdrant/Milvus etc. in [docker/docker-compose.yaml](cci:7://file:///Users/hren/Downloads/dify/docker/docker-compose.yaml:0:0-0:0)  
  - Background indexing/cleanup tasks: [api/tasks/](cci:7://file:///Users/hren/Downloads/dify/api/tasks:0:0-0:0), [api/schedule/](cci:7://file:///Users/hren/Downloads/dify/api/schedule:0:0-0:0)

- **Operational maturity (LLMOps)**  
  Logging, tracing, and quality workflows to improve prompts and apps over time.  
  - Sentry + OTEL: `api/extensions/ext_sentry.py`, `api/extensions/ext_otel.py`, env in [docker/.env.example](cci:7://file:///Users/hren/Downloads/dify/docker/.env.example:0:0-0:0) and [docker/docker-compose.yaml](cci:7://file:///Users/hren/Downloads/dify/docker/docker-compose.yaml:0:0-0:0)  
  - Dataset and annotation services: [api/services/dataset_service.py](cci:7://file:///Users/hren/Downloads/dify/api/services/dataset_service.py:0:0-0:0), [api/services/annotation_service.py](cci:7://file:///Users/hren/Downloads/dify/api/services/annotation_service.py:0:0-0:0)

- **Secure, self-hosted control**  
  Run fully on your infra with hardened defaults.  
  - Env-driven config: [api/configs/](cci:7://file:///Users/hren/Downloads/dify/api/configs:0:0-0:0), [docker/.env.example](cci:7://file:///Users/hren/Downloads/dify/docker/.env.example:0:0-0:0)  
  - SSRF proxy and code sandbox: [docker/ssrf_proxy/](cci:7://file:///Users/hren/Downloads/dify/docker/ssrf_proxy:0:0-0:0), [docker/docker-compose.yaml](cci:7://file:///Users/hren/Downloads/dify/docker/docker-compose.yaml:0:0-0:0) (`CODE_EXECUTION_*`)  
  - CSP and X-Frame controls: [web/middleware.ts](cci:7://file:///Users/hren/Downloads/dify/web/middleware.ts:0:0-0:0)

- **Scale and reliability**  
  Async workers and composable services scale for heavy workloads.  
  - Celery workers: `api/extensions/ext_celery.py`, tasks in [api/tasks/](cci:7://file:///Users/hren/Downloads/dify/api/tasks:0:0-0:0)  
  - Nginx fronting web/api, Redis, Postgres, vector DBs: [docker/docker-compose.yaml](cci:7://file:///Users/hren/Downloads/dify/docker/docker-compose.yaml:0:0-0:0)

# Who Benefits

- **Product teams** shipping AI copilots, chat assistants, and knowledge bots quickly.  
- **Platform/ML engineers** needing a governed, observable, and extensible LLM runtime.  
- **Enterprises** wanting self-hosted control with integrations to their storage, databases, and observability stack.

# Grounding

- Description and capabilities: [README.md](cci:7://file:///Users/hren/Downloads/dify/README.md:0:0-0:0) (features: Workflow, RAG, Agents, LLMOps, Backend-as-a-Service).  
- Backend layering and routes: [api/app_factory.py](cci:7://file:///Users/hren/Downloads/dify/api/app_factory.py:0:0-0:0), [api/extensions/ext_blueprints.py](cci:7://file:///Users/hren/Downloads/dify/api/extensions/ext_blueprints.py:0:0-0:0), `api/services/*`, `api/models/*`.  
- Frontend integration and API prefixes: [web/README.md](cci:7://file:///Users/hren/Downloads/dify/web/README.md:0:0-0:0), [web/package.json](cci:7://file:///Users/hren/Downloads/dify/web/package.json:0:0-0:0), `web/service/*`.  
- Deployment and infra options: [docker/docker-compose.yaml](cci:7://file:///Users/hren/Downloads/dify/docker/docker-compose.yaml:0:0-0:0), [docker/README.md](cci:7://file:///Users/hren/Downloads/dify/docker/README.md:0:0-0:0).

# Summary

- Provided the core use case: build and operate LLM apps (workflows, agents, RAG) quickly.  
- Outlined key value pillars: speed, ecosystem breadth, RAG-first, LLMOps, security/self-hosting, and scalability.  
- Cited concrete files/paths so you can verify or explore further.

### User Input

What agentic framework does it use? LangGraph or something else?

### Planner Response

I'll check the backend source under [api/core/agent/](cci:7://file:///Users/hren/Downloads/dify/api/core/agent:0:0-0:0) and [api/core/workflow/](cci:7://file:///Users/hren/Downloads/dify/api/core/workflow:0:0-0:0) to see if it imports LangGraph or implements its own agent and graph execution.

*Listed directory [agent](file:///Users/hren/Downloads/dify/api/core/agent) *

### Planner Response

I'll search the codebase for references to LangGraph or other agent frameworks, and inspect the workflow/agent engine to confirm if it's custom.

*Grep searched codebase*

*Grep searched codebase*

*Grep searched codebase*

*Grep searched codebase*

*Grep searched codebase*

*Grep searched codebase*

*Listed directory [strategy](file:///Users/hren/Downloads/dify/api/core/agent/strategy) *

*Viewed [base_agent_runner.py](file:///Users/hren/Downloads/dify/api/core/agent/base_agent_runner.py) *

*Listed directory [workflow](file:///Users/hren/Downloads/dify/api/core/workflow) *

### Planner Response

# Findings

- **Short answer**: It uses Dify’s own agent and workflow engines, not LangGraph.
- **Evidence**:
  - No references to LangGraph/LangChain/Haystack/LlamaIndex in the repo search.
  - Custom workflow engine under [api/core/workflow/graph_engine/](cci:7://file:///Users/hren/Downloads/dify/api/core/workflow/graph_engine:0:0-0:0) (e.g., [graph_engine.py](cci:7://file:///Users/hren/Downloads/dify/api/core/workflow/graph_engine/graph_engine.py:0:0-0:0), [manager.py](cci:7://file:///Users/hren/Downloads/dify/api/core/workflow/graph_engine/manager.py:0:0-0:0), command channels, ready queue, layers).
  - Agent runners under [api/core/agent/](cci:7://file:///Users/hren/Downloads/dify/api/core/agent:0:0-0:0):
    - Function calling: [api/core/agent/fc_agent_runner.py](cci:7://file:///Users/hren/Downloads/dify/api/core/agent/fc_agent_runner.py:0:0-0:0)
    - ReAct/chain-of-thought: [api/core/agent/cot_agent_runner.py](cci:7://file:///Users/hren/Downloads/dify/api/core/agent/cot_agent_runner.py:0:0-0:0) and [cot_chat_agent_runner.py](cci:7://file:///Users/hren/Downloads/dify/api/core/agent/cot_chat_agent_runner.py:0:0-0:0)
    - Base orchestration: [api/core/agent/base_agent_runner.py](cci:7://file:///Users/hren/Downloads/dify/api/core/agent/base_agent_runner.py:0:0-0:0), strategies in [api/core/agent/strategy/](cci:7://file:///Users/hren/Downloads/dify/api/core/agent/strategy:0:0-0:0)
  - Tools system is native: [api/core/tools/](cci:7://file:///Users/hren/Downloads/dify/api/core/tools:0:0-0:0), orchestrated via `core/tools/tool_manager.py`, plus dataset retriever tool in `core/tools/utils/dataset_retriever_tool.py`.
  - Visual workflow uses its own graph runtime entrypoint [api/core/workflow/workflow_entry.py](cci:7://file:///Users/hren/Downloads/dify/api/core/workflow/workflow_entry.py:0:0-0:0).

# What it uses instead

- **Custom workflow graph engine**
  - Paths: `api/core/workflow/graph_engine/*`, `api/core/workflow/graph/*`
  - Features: event-driven execution, persistence, ready-queue, Redis/in-memory command channels, execution limits, debug logging layers.
- **Custom agent runners**
  - Supports both LLM function-calling and ReAct-style reasoning via purpose-built runners.
  - Integrates tool calls, dataset retrieval, and message history formatting directly into prompt construction.

# Tooling and interoperability

- **Built-in tools**: [api/core/tools/](cci:7://file:///Users/hren/Downloads/dify/api/core/tools:0:0-0:0) (search, image generation, web fetchers, etc.).
- **RAG integration**: native ingestion/retrieval in [api/core/rag/](cci:7://file:///Users/hren/Downloads/dify/api/core/rag:0:0-0:0) with vector DB adapters (Weaviate/Qdrant/Milvus/etc.).
- **MCP support**: endpoints in [api/controllers/mcp/](cci:7://file:///Users/hren/Downloads/dify/api/controllers/mcp:0:0-0:0) for Model Context Protocol-style tool access.
- No dependency on LangGraph; composition happens through Dify’s own workflow nodes and agent runners.

# Relevant paths to inspect

- **Workflow engine**: [api/core/workflow/graph_engine/graph_engine.py](cci:7://file:///Users/hren/Downloads/dify/api/core/workflow/graph_engine/graph_engine.py:0:0-0:0), [api/core/workflow/graph_engine/manager.py](cci:7://file:///Users/hren/Downloads/dify/api/core/workflow/graph_engine/manager.py:0:0-0:0)
- **Agent runners**: [api/core/agent/fc_agent_runner.py](cci:7://file:///Users/hren/Downloads/dify/api/core/agent/fc_agent_runner.py:0:0-0:0), [api/core/agent/cot_agent_runner.py](cci:7://file:///Users/hren/Downloads/dify/api/core/agent/cot_agent_runner.py:0:0-0:0), [api/core/agent/base_agent_runner.py](cci:7://file:///Users/hren/Downloads/dify/api/core/agent/base_agent_runner.py:0:0-0:0)
- **Tools**: [api/core/tools/](cci:7://file:///Users/hren/Downloads/dify/api/core/tools:0:0-0:0), `api/core/tools/tool_manager.py`
- **Workflow entry**: [api/core/workflow/workflow_entry.py](cci:7://file:///Users/hren/Downloads/dify/api/core/workflow/workflow_entry.py:0:0-0:0)

# Summary

- **Dify implements its own agentic orchestration and workflow graph engine.**
- It supports LLM function-calling and ReAct via custom runners, and a first-class visual workflow runtime—no LangGraph required.

### User Input

Does people use this because it has both the frontend and backend implmented for chatbot?

### Planner Response

# Short answer
Yes—many choose Dify because it’s a full‑stack LLM app platform: it ships both a production‑ready backend and a frontend console/UI for chat, workflows, and app management. But the stronger reason is the end‑to‑end feature set around that stack.

# Why people use it

- **Full-stack out of the box**
  - **Frontend**: Next.js console and app UI to build, test, and run chat/agent/RAG apps.
    - Paths: [web/app/](cci:7://file:///Users/hren/Downloads/dify/web/app:0:0-0:0), `web/service/*`, CSP/iframe logic in [web/middleware.ts](cci:7://file:///Users/hren/Downloads/dify/web/middleware.ts:0:0-0:0) (explicitly allows `/chat`, [/workflow](cci:7://file:///Users/hren/Downloads/dify/api/core/workflow:0:0-0:0), `/completion`, `/webapp-signin` to be embedded).
  - **Backend**: Flask API with clean layering, Celery workers, storage/vector DB integrations.
    - Paths: `api/controllers/*`, `api/services/*`, `api/models/*`, tasks in `api/tasks/*`.
  - **API separation** for console vs public app:
    - `NEXT_PUBLIC_API_PREFIX` (console), `NEXT_PUBLIC_PUBLIC_API_PREFIX` (public runtime) in [web/README.md](cci:7://file:///Users/hren/Downloads/dify/web/README.md:0:0-0:0).
    - Blueprints: `controllers.console`, `controllers.web`, `controllers.service_api` in [api/extensions/ext_blueprints.py](cci:7://file:///Users/hren/Downloads/dify/api/extensions/ext_blueprints.py:0:0-0:0).

- **Agentic workflows without extra glue**
  - **Custom workflow engine**: `api/core/workflow/graph_engine/*`, nodes in `api/core/workflow/nodes/*`.
  - **Agents**: function-calling and ReAct runners.
    - Paths: [api/core/agent/fc_agent_runner.py](cci:7://file:///Users/hren/Downloads/dify/api/core/agent/fc_agent_runner.py:0:0-0:0), [api/core/agent/cot_agent_runner.py](cci:7://file:///Users/hren/Downloads/dify/api/core/agent/cot_agent_runner.py:0:0-0:0), [base_agent_runner.py](cci:7://file:///Users/hren/Downloads/dify/api/core/agent/base_agent_runner.py:0:0-0:0).
  - **Tools ecosystem**: built-ins and plugins, dataset retrievers.
    - Paths: `api/core/tools/*`, `api/core/tools/tool_manager.py`.

- **RAG pipeline built-in**
  - Ingestion, chunking, retrievers, vector DB adapters (Weaviate/Qdrant/Milvus/etc.).
  - Paths: `api/core/rag/*`, DB adapters via [api/pyproject.toml](cci:7://file:///Users/hren/Downloads/dify/api/pyproject.toml:0:0-0:0) vdb group; compose services in [docker/docker-compose.yaml](cci:7://file:///Users/hren/Downloads/dify/docker/docker-compose.yaml:0:0-0:0).

- **Operational features for production**
  - Tracing/observability and governance.
    - Sentry/OTEL extensions, ops service: `api/extensions/ext_sentry.py`, `api/extensions/ext_otel.py`, [api/services/ops_service.py](cci:7://file:///Users/hren/Downloads/dify/api/services/ops_service.py:0:0-0:0).
  - Datasets, annotations, evaluations.
    - Paths: [api/services/dataset_service.py](cci:7://file:///Users/hren/Downloads/dify/api/services/dataset_service.py:0:0-0:0), [api/services/annotation_service.py](cci:7://file:///Users/hren/Downloads/dify/api/services/annotation_service.py:0:0-0:0).

- **Self-hosted and deployable**
  - Docker Compose for API, web, workers, Nginx, Postgres, Redis, vector DBs.
    - Paths: [docker/docker-compose.yaml](cci:7://file:///Users/hren/Downloads/dify/docker/docker-compose.yaml:0:0-0:0), env in [docker/.env.example](cci:7://file:///Users/hren/Downloads/dify/docker/.env.example:0:0-0:0).
  - SSRF proxy and code sandboxing knobs baked in (security controls).

- **Headless is supported**
  - If you already have a UI, you can consume the backend via REST or SDKs.
    - SDKs: [sdks/python-client/](cci:7://file:///Users/hren/Downloads/dify/sdks/python-client:0:0-0:0), [sdks/nodejs-client/](cci:7://file:///Users/hren/Downloads/dify/sdks/nodejs-client:0:0-0:0), [sdks/php-client/](cci:7://file:///Users/hren/Downloads/dify/sdks/php-client:0:0-0:0).

# Typical usage patterns

- **All-in-one**: Use Dify’s web console + public app UI and the backend to ship a chatbot/agent fast.
- **Headless**: Author workflows/agents in the console, then call [service_api](cci:7://file:///Users/hren/Downloads/dify/api/controllers/service_api:0:0-0:0) from your own frontend.
- **Hybrid**: Start with the built-in UI for speed, migrate to a custom UI later while keeping the same backend workflows and data.

# Summary
- People do use Dify because it includes both frontend and backend for chat/agent apps.
- The bigger value is the integrated workflow/agent engine, RAG, tools, ops/observability, and turnkey deployment—so teams can go from prototype to production quickly, with or without bringing their own UI.

### User Input

I have implemented RAG from scratch on my own. I went through the process of chunk the text, generate embeddings and save both the text and embeddings to AWS Opensearch. 

If I want to use RAG using dify, how would I go about doing it? Say that I have multiple Markdown files



*Grep searched codebase*

### Planner Response

# How to use RAG in Dify (with multiple Markdown files)

You have two main paths: use Dify’s built‑in Datasets (point‑and‑click + background indexing) or build a Workflow with explicit “index” and “retrieve” nodes. Both ultimately push chunks/embeddings into your configured vector DB (OpenSearch supported).

## Prereqs: configure OpenSearch
- Set vector store to OpenSearch and configure credentials.
  - File: [docker/.env.example](cci:7://file:///Users/hren/Downloads/dify/docker/.env.example:0:0-0:0), [docker/docker-compose.yaml](cci:7://file:///Users/hren/Downloads/dify/docker/docker-compose.yaml:0:0-0:0)
  - Key envs: `VECTOR_STORE=opensearch`, `OPENSEARCH_HOST`, `OPENSEARCH_PORT`, `OPENSEARCH_SECURE`, `OPENSEARCH_VERIFY_CERTS`, `OPENSEARCH_AUTH_METHOD` (basic/aws-sigv4), `OPENSEARCH_AWS_REGION`, `OPENSEARCH_AWS_SERVICE`.
- Dify supports Markdown parsing out of the box (see [api/pyproject.toml](cci:7://file:///Users/hren/Downloads/dify/api/pyproject.toml:0:0-0:0) includes `unstructured[...md...]`).

## Option A: Datasets (simplest, recommended)
- In Web console:
  - Create a Dataset, upload your Markdown files (bulk is fine).  
    The backend handles chunking, embedding, and vector upsert asynchronously.
    - Ingestion/indexing tasks: [api/tasks/document_indexing_task.py](cci:7://file:///Users/hren/Downloads/dify/api/tasks/document_indexing_task.py:0:0-0:0), [api/tasks/create_segment_to_index_task.py](cci:7://file:///Users/hren/Downloads/dify/api/tasks/create_segment_to_index_task.py:0:0-0:0), etc.
  - Choose chunking and embedding settings (provider configured in “Model Providers”).
- Use in apps/workflows:
  - Attach the Dataset to a Chat/Agent app. Retrieval is auto-wired at runtime.
    - Agent integration uses `DatasetRetrieverTool` under the hood: `api/core/tools/utils/dataset_retriever_tool.py`, used by [core.agent.base_agent_runner.BaseAgentRunner](cci:2://file:///Users/hren/Downloads/dify/api/core/agent/base_agent_runner.py:48:0-527:65).
  - Or reference the Dataset from a Workflow (see Option B).

## Option B: Visual Workflow (fine-grained control)
- Build a graph in the Workflow editor:
  - Use `knowledge_index` when you want dynamic ingestion in‑flow (optional):
    - [api/core/workflow/nodes/knowledge_index/knowledge_index_node.py](cci:7://file:///Users/hren/Downloads/dify/api/core/workflow/nodes/knowledge_index/knowledge_index_node.py:0:0-0:0)
  - Use `knowledge_retrieval` to retrieve context from a Dataset:
    - [api/core/workflow/nodes/knowledge_retrieval/knowledge_retrieval_node.py](cci:7://file:///Users/hren/Downloads/dify/api/core/workflow/nodes/knowledge_retrieval/knowledge_retrieval_node.py:0:0-0:0)
  - Feed retrieved context into an `llm` node to answer queries.
- Tune retrieval params (top‑k, filters) in the node config. Execution is managed by the graph engine:
  - `api/core/workflow/graph_engine/*`, entrypoint [api/core/workflow/workflow_entry.py](cci:7://file:///Users/hren/Downloads/dify/api/core/workflow/workflow_entry.py:0:0-0:0).

## Option C: Headless ingestion via API/SDK
- Programmatically create datasets, upload files, and trigger indexing using the REST APIs/SDKs:
  - SDKs: [sdks/python-client/](cci:7://file:///Users/hren/Downloads/dify/sdks/python-client:0:0-0:0), [sdks/nodejs-client/](cci:7://file:///Users/hren/Downloads/dify/sdks/nodejs-client:0:0-0:0), [sdks/php-client/](cci:7://file:///Users/hren/Downloads/dify/sdks/php-client:0:0-0:0).
- Best when you need CI/CD ingestion pipelines or large batch imports.

## Using an existing AWS OpenSearch index
- Easiest path: re‑import your Markdown into a Dify Dataset and let Dify re‑embed and index (guarantees schema compatibility).
- If you must reuse your existing index:
  - Ensure dimensions, fields, and similarity config match Dify’s expectations for OpenSearch.
  - You may need a custom connector or to align field names to Dify’s retriever. Dify’s native OpenSearch client lives under RAG VDB adapters:
    - `api/core/rag/datasource/vdb/opensearch/`
  - In practice, teams usually let Dify own the RAG index to simplify maintenance.

## Quick checklist
- Configure OpenSearch envs (and embedding provider) → start Dify ([docker/docker-compose.yaml](cci:7://file:///Users/hren/Downloads/dify/docker/docker-compose.yaml:0:0-0:0)).
- Create Dataset → upload Markdown files → wait for indexing.
- Build a Chat/Agent app and attach the Dataset, or create a Workflow with `knowledge_retrieval` → `llm`.
- Test retrieval quality; adjust chunk size/overlap and top‑k as needed.

# Relevant paths
- Vector DB selection: [docker/docker-compose.yaml](cci:7://file:///Users/hren/Downloads/dify/docker/docker-compose.yaml:0:0-0:0), [docker/.env.example](cci:7://file:///Users/hren/Downloads/dify/docker/.env.example:0:0-0:0)
- RAG pipeline internals: `api/core/rag/*`
- Workflow nodes: [api/core/workflow/nodes/knowledge_index/knowledge_index_node.py](cci:7://file:///Users/hren/Downloads/dify/api/core/workflow/nodes/knowledge_index/knowledge_index_node.py:0:0-0:0), `.../knowledge_retrieval/knowledge_retrieval_node.py`
- Agent + dataset tool: [api/core/agent/base_agent_runner.py](cci:7://file:///Users/hren/Downloads/dify/api/core/agent/base_agent_runner.py:0:0-0:0), `api/core/tools/utils/dataset_retriever_tool.py`
- Indexing tasks: `api/tasks/*document_index*`

# Summary
- Yes, Dify will do chunking, embedding, and OpenSearch upsert for your Markdown via Datasets or Workflow nodes.
- Start with Datasets (Option A) for the fastest path; use Workflows (Option B) for custom control; use SDKs (Option C) for programmatic pipelines.

### User Input

I don't want to use OpenSearch. I just need to know that a process exists to upload documents. What are the format requirements? Is dify following the best practice for chunking and indexing?

*Grep searched codebase*

### Planner Response

I'll scan the backend services and controllers for datasets and ingestion to answer: accepted file formats, upload process, and how chunking/indexing is done. I’ll open [api/services/dataset_service.py](cci:7://file:///Users/hren/Downloads/dify/api/services/dataset_service.py:0:0-0:0) and relevant controllers, plus look at RAG nodes docs.

*Searched filesystem*

*Listed directory [file](file:///Users/hren/Downloads/dify/api/core/file) *

### Planner Response

I’ll open [api/services/dataset_service.py](cci:7://file:///Users/hren/Downloads/dify/api/services/dataset_service.py:0:0-0:0) and related file handling modules to verify supported file formats, ingestion pipeline, and chunking/indexing parameters so I can answer with concrete paths and behaviors.

*Viewed [dataset_service.py](file:///Users/hren/Downloads/dify/api/services/dataset_service.py) *

*Grep searched codebase*

### Planner Response

I'll search the backend for the ingestion and chunking pipeline implementation to answer supported formats, upload process, and whether chunking/indexing follows best practices. In particular, I'll look under `api/core/rag/index_processor/` and for any [DocumentService](cci:2://file:///Users/hren/Downloads/dify/api/services/dataset_service.py:1068:0-2597:26) or processing rules used by datasets.

*Grep searched codebase*

*Grep searched codebase*

### Planner Response

I'll open dataset and file-related controllers and helpers to confirm supported file formats, how uploads work, and the chunking/indexing pipeline details. This ensures my answer is grounded in the repo’s code.

*Viewed [datasets_document.py](file:///Users/hren/Downloads/dify/api/controllers/console/datasets/datasets_document.py) *

*Listed directory [rag](file:///Users/hren/Downloads/dify/api/core/rag) *

*Grep searched codebase*

*Grep searched codebase*

### Planner Response

To provide concrete guidance on supported document formats, upload process, and chunking/indexing best practices, I’ll open the remaining part of [api/services/dataset_service.py](cci:7://file:///Users/hren/Downloads/dify/api/services/dataset_service.py:0:0-0:0) to find `DocumentService.DEFAULT_RULES`, and scan RAG components for format support and split settings under [api/core/rag/extractor/](cci:7://file:///Users/hren/Downloads/dify/api/core/rag/extractor:0:0-0:0) and [api/core/rag/splitter/](cci:7://file:///Users/hren/Downloads/dify/api/core/rag/splitter:0:0-0:0).

*Viewed [dataset_service.py](file:///Users/hren/Downloads/dify/api/services/dataset_service.py) *

### Planner Response

To answer precisely about supported formats and chunking/indexing behavior, I’ll quickly list the RAG extractor and splitter modules to confirm file types and splitting strategies implemented.

*Listed directory [extractor](file:///Users/hren/Downloads/dify/api/core/rag/extractor) *

*Listed directory [unstructured](file:///Users/hren/Downloads/dify/api/core/rag/extractor/unstructured) *

*Listed directory [files](file:///Users/hren/Downloads/dify/api/controllers/files) *

*Listed directory [splitter](file:///Users/hren/Downloads/dify/api/core/rag/splitter) *

*Viewed [upload.py](file:///Users/hren/Downloads/dify/api/controllers/files/upload.py) *

### Planner Response

# Short answer
- Yes, Dify has a built-in document upload and RAG pipeline.
- You’re not tied to OpenSearch; you can pick other vector stores (Weaviate, Qdrant, Milvus, pgvector, etc.) or just rely on the upload/indexing process itself.

# Supported document formats
Dify extracts text from many formats and sources. Core extractors are in [api/core/rag/extractor/](cci:7://file:///Users/hren/Downloads/dify/api/core/rag/extractor:0:0-0:0):
- **Direct files**: [markdown_extractor.py](cci:7://file:///Users/hren/Downloads/dify/api/core/rag/extractor/markdown_extractor.py:0:0-0:0), [pdf_extractor.py](cci:7://file:///Users/hren/Downloads/dify/api/core/rag/extractor/pdf_extractor.py:0:0-0:0), [text_extractor.py](cci:7://file:///Users/hren/Downloads/dify/api/core/rag/extractor/text_extractor.py:0:0-0:0), [csv_extractor.py](cci:7://file:///Users/hren/Downloads/dify/api/core/rag/extractor/csv_extractor.py:0:0-0:0), [excel_extractor.py](cci:7://file:///Users/hren/Downloads/dify/api/core/rag/extractor/excel_extractor.py:0:0-0:0), [word_extractor.py](cci:7://file:///Users/hren/Downloads/dify/api/core/rag/extractor/word_extractor.py:0:0-0:0), [html_extractor.py](cci:7://file:///Users/hren/Downloads/dify/api/core/rag/extractor/html_extractor.py:0:0-0:0).
- **Unstructured-based**: [unstructured_markdown_extractor.py](cci:7://file:///Users/hren/Downloads/dify/api/core/rag/extractor/unstructured/unstructured_markdown_extractor.py:0:0-0:0), [unstructured_epub_extractor.py](cci:7://file:///Users/hren/Downloads/dify/api/core/rag/extractor/unstructured/unstructured_epub_extractor.py:0:0-0:0), `unstructured_ppt(_x)_extractor.py`, [unstructured_eml_extractor.py](cci:7://file:///Users/hren/Downloads/dify/api/core/rag/extractor/unstructured/unstructured_eml_extractor.py:0:0-0:0), [unstructured_xml_extractor.py](cci:7://file:///Users/hren/Downloads/dify/api/core/rag/extractor/unstructured/unstructured_xml_extractor.py:0:0-0:0) under [api/core/rag/extractor/unstructured/](cci:7://file:///Users/hren/Downloads/dify/api/core/rag/extractor/unstructured:0:0-0:0).
- **External sources**: [notion_extractor.py](cci:7://file:///Users/hren/Downloads/dify/api/core/rag/extractor/notion_extractor.py:0:0-0:0), website crawlers ([firecrawl/](cci:7://file:///Users/hren/Downloads/dify/api/core/rag/extractor/firecrawl:0:0-0:0), [jina_reader_extractor.py](cci:7://file:///Users/hren/Downloads/dify/api/core/rag/extractor/jina_reader_extractor.py:0:0-0:0), [watercrawl/](cci:7://file:///Users/hren/Downloads/dify/api/core/rag/extractor/watercrawl:0:0-0:0)).

In short: Markdown, TXT, PDF, DOCX, CSV, XLSX, HTML, PPT/PPTX, EPUB, EML, XML, and more are supported.

# Upload process (no OpenSearch required)
You can upload via the console or API; the backend handles parsing, cleaning, splitting, embedding, and indexing asynchronously.
- Console/API endpoints: see [api/controllers/console/datasets/datasets_document.py](cci:7://file:///Users/hren/Downloads/dify/api/controllers/console/datasets/datasets_document.py:0:0-0:0).
  - Create a dataset → upload files (or point to Notion/website) → pick indexing technique and process rules → Dify runs background indexing tasks (`api/tasks/*document_index*`).
  - Indexing estimator and status endpoints are implemented in the same controller.
- File upload infra: [api/controllers/files/upload.py](cci:7://file:///Users/hren/Downloads/dify/api/controllers/files/upload.py:0:0-0:0) (plus signed URLs and size/type validation).

Relevant limits are configurable:
- `UPLOAD_FILE_SIZE_LIMIT`, `UPLOAD_FILE_BATCH_LIMIT`, etc. in [docker/docker-compose.yaml](cci:7://file:///Users/hren/Downloads/dify/docker/docker-compose.yaml:0:0-0:0).
- Indexing segmentation cap: `INDEXING_MAX_SEGMENTATION_TOKENS_LENGTH` in `DocumentService.DEFAULT_RULES` via `dify_config` ([api/services/dataset_service.py](cci:7://file:///Users/hren/Downloads/dify/api/services/dataset_service.py:0:0-0:0)).

# Format and processing requirements
- Files must be one of the supported types above and within configured size limits.
- Encodings should be valid (UTF-8 recommended).
- Preprocessing rules are applied before chunking:
  - Defaults: remove extra spaces (on), remove URLs/emails (off).
  - See `DocumentService.DEFAULT_RULES` in [api/services/dataset_service.py](cci:7://file:///Users/hren/Downloads/dify/api/services/dataset_service.py:0:0-0:0):
    - `segmentation.max_tokens = 1024`
    - `segmentation.chunk_overlap = 50`
    - `segmentation.delimiter = "\n"`
    - `mode = "custom"` (also accepts `"hierarchical"`).
- You select an indexing technique per dataset:
  - `"high_quality"` → embedding-based semantic search (requires an embedding model).
  - `"economy"` → keyword-based indexing.
  - Logic and validation: [DatasetService](cci:2://file:///Users/hren/Downloads/dify/api/services/dataset_service.py:92:0-1065:9) in [api/services/dataset_service.py](cci:7://file:///Users/hren/Downloads/dify/api/services/dataset_service.py:0:0-0:0).

# Is Dify following chunking/indexing best practices?
- Yes, it implements widely recommended defaults and options:
  - **Token-based chunks with overlap** by default (1024 tokens, 50 overlap), adjustable via process rules: `DocumentService.DEFAULT_RULES` in [api/services/dataset_service.py](cci:7://file:///Users/hren/Downloads/dify/api/services/dataset_service.py:0:0-0:0).
  - **Hierarchical segmentation** supported (`process_rule.mode` allows `"hierarchical"`), which enables parent/child chunking patterns common in advanced RAG.
  - **Semantic retrieval + reranking**: the retrieval model supports semantic search and optional reranking with configurable `top_k` (set on dataset creation/update). See `RetrievalMethod` and `RetrievalModel` usage in [api/services/dataset_service.py](cci:7://file:///Users/hren/Downloads/dify/api/services/dataset_service.py:0:0-0:0).
  - **Background, resumable indexing** with detailed status and error handling (`api/tasks/*`, [indexing_runner.py](cci:7://file:///Users/hren/Downloads/dify/api/core/indexing_runner.py:0:0-0:0)).
  - **Multiple vector stores** supported (choose what fits your infra and latency/feature needs). No lock-in to OpenSearch.

# Recommended usage for Markdown
- **Use "high_quality"** indexing with a strong embedding model for semantic retrieval.
- **Start with 512–1024 token chunks** and 50–100 token overlap; adjust based on answer quality.
- Consider **hierarchical** mode if your Markdown has headings/sections you want to preserve for better context windows.
- Tune **retrieval top_k** (e.g., 4–8) and enable **reranking** if your corpus is diverse or noisy.

# Where to configure in the code
- **Process rules and defaults**: `DocumentService.DEFAULT_RULES` in [api/services/dataset_service.py](cci:7://file:///Users/hren/Downloads/dify/api/services/dataset_service.py:0:0-0:0).
- **Extractors**: `api/core/rag/extractor/*` and `api/core/rag/extractor/unstructured/*`.
- **Splitters**: [api/core/rag/splitter/text_splitter.py](cci:7://file:///Users/hren/Downloads/dify/api/core/rag/splitter/text_splitter.py:0:0-0:0), [fixed_text_splitter.py](cci:7://file:///Users/hren/Downloads/dify/api/core/rag/splitter/fixed_text_splitter.py:0:0-0:0).
- **Indexing runner and tasks**: [api/core/indexing_runner.py](cci:7://file:///Users/hren/Downloads/dify/api/core/indexing_runner.py:0:0-0:0), [api/tasks/document_indexing_task.py](cci:7://file:///Users/hren/Downloads/dify/api/tasks/document_indexing_task.py:0:0-0:0), `..._create_segment_to_index_task.py`.
- **Dataset APIs**: [api/controllers/console/datasets/datasets_document.py](cci:7://file:///Users/hren/Downloads/dify/api/controllers/console/datasets/datasets_document.py:0:0-0:0).

# Summary
- You can upload Markdown and many other formats; Dify parses, cleans, chunks, embeds, and indexes them asynchronously.
- You’re not required to use OpenSearch; the process is decoupled from the specific vector store.
- Defaults (token-based chunking with overlap, optional hierarchical segmentation, semantic retrieval with optional reranking) align with common RAG best practices and are configurable per dataset.