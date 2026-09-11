# Implementation Plan: Months 3–6 Full Stack Training Program

## 0. Context & Review of Existing Material

### Existing repository state
```
full-stack-training-program/
├── README.md                              (219 lines — program overview, 6-month structure, tech stack, repo tree, career outcomes)
├── 00-Setup-Environment/README.md         (309 lines — Git, VSCode, Node, Python, PostgreSQL, MongoDB, Docker, AI tools, verification checklist)
├── 01-Month-1-Frontend-Fundamentals/README.md   (1436 lines — HTML/CSS/JS fundamentals)
├── 02-Month-2-Advanced-Frontend/README.md        (1266 lines — Advanced JS, React, Redux, Router)
└── 02-Month-2-Advanced-Frontend/MINI-PROJECT-TODO-APP.md  (880 lines — full code walkthrough)
```

### Established conventions (to replicate exactly)
1. **Folder naming**: zero-padded number + `Month-X-` + kebab-case descriptive name.
   - `01-Month-1-Frontend-Fundamentals`
   - `02-Month-2-Advanced-Frontend`
   - **→ 03-Month-3-Backend-Basics**, **→ 04-Month-4-Advanced-Backend**, **→ 05-Month-5-Databases-DevOps**, **→ 06-Month-6-Capstone-Projects**
2. **README.md structure** (consistent in Month 1 & Month 2):
   - H1: `# Month X: Title`  then  H2: `## Technology Descriptions`
   - Metadata block of 3 bold lines: `**Duration:**`, `**Daily Time Commitment:**`, `**Expected Outcome:**`
   - `## 🎯 Month X Learning Objectives` (✅ checklist, 8–10 items)
   - `## 📋 Week-by-Week Breakdown` containing 4 `### **Week N: Topic**` sections
   - Each week: `#### **Days X-Y: Subtopic**` blocks with **Topics Covered**, code examples (```javascript / ```python / ```bash), Practice Exercises, and Project assignments
   - `## 📝 Month N Assignments` (detailed: Requirements + Submission)
   - `## 🎓 Month N Projects Summary` (numbered list, 6–11 projects)
   - `## 📊 Key Concepts Review` (categorised by domain, ✅ checkmarks)
   - `## ✅ Month N Progress Checklist` (checkbox list)
   - `## 🎯 Next Steps` (emoji, next-month link)
   - Footer: `*Last Updated: June 2026*`
3. **Mini-project files**: Month 2 ships a `MINI-PROJECT-<NAME>.md` with: Overview, Features, Project Structure tree, Setup Instructions, per-file Implementation code blocks, Key Features, Learning Outcomes. Months 3–4 should each include one.
4. **Code style**: code blocks labelled with language tags; realistic, copy-pasteable examples; inline comments kept minimal; emphasis on industry best-practice commands.
5. **Projects** scale progressive complexity; each ends with deploy instruction line.
6. **Duration model**: 4 weeks ≈ 26 days per month; 6–8 hrs/day; 1000+ hrs total for 6 months.

### README "Program Structure" reference (from root README)
- Month 3: Backend Basics (Python, Django, REST APIs)
- Month 4: Advanced Backend (FastAPI, Authentication, Async)
- Month 5: Databases & DevOps (PostgreSQL, MongoDB, Docker, CI/CD)
- Month 6: Capstone Projects & Deployment (Real-world applications)

### Tech stack reference (from root README)
- Backend: Python (OOP, Async), Django + Django REST Framework, Flask, FastAPI, JWT, Middleware
- Database: PostgreSQL (SQLAlchemy, Django ORM), MongoDB, schemas, relationships, migrations, query optimization
- DevOps: Git/GitHub Workflow, Linux, Docker + Compose, Nginx, CI/CD GitHub Actions, AWS/Azure, SSL, Domain config
- AI Tools: ChatGPT, GitHub Copilot, Cursor AI (carry through all months like existing content).

---

## 1. Month 3 — Backend Basics (Python, Django, REST APIs)

### Folder
`03-Month-3-Backend-Basics/` → README.md (+ MINI-PROJECT-BLOG-API.md)

### README.md outline (target ~1100–1300 lines)

**Header / Metadata / Objectives** (same template).
Learning objectives:
- ✅ Master Python core for backend development
- ✅ Understand OOP, modules, packages, virtual environments
- ✅ Build REST APIs with Django & Django REST Framework
- ✅ Design and query relational models with Django ORM
- ✅ Implement serializers, viewsets, routers
- ✅ Apply authentication, permissions, throttling
- ✅ Write unit & integration tests
- ✅ Document APIs with Swagger/OpenAPI
- ✅ Deploy Django to production (Gunicorn/Nginx)
- ✅ Build 5+ backend projects with best practices

**Week 1 — Python Fundamentals for Backend** (Days 1-7)
- Days 1-2: Python basics — variables, data types, operators, control flow, functions, `venv`/`pip`/`requirements.txt`. Show `python -m venv`, `pip freeze`, `.gitignore` with `__pycache__/`.
- Days 3-4: OOP — classes, `__init__`, methods, inheritance, `super()`, properties, dunder methods, `@classmethod`/`@staticmethod`. Show a `BankAccount` OOP example.
- Days 5-7: Data structures & file I/O — lists, dicts, sets, tuples; list/dict comprehensions; reading/writing JSON & CSV; exception handling (`try/except/else/finally`); logging. Show `logging.basicConfig`, JSON CRUD on a file-based "database".

**Week 2 — Django Fundamentals** (Days 8-14)
- Days 8-9: Project setup — `django-admin startproject`, `startapp`, `settings.py` (env vars via `python-decouple`/`os.environ`), `INSTALLED_APPS`, templates/static dirs.
- Days 10-11: Models & ORM — `models.Model`, field types, relationships (ForeignKey/ManyToMany/OneToOne), `save()`, `objects.all/filter/get/exclude`, `select_related`/`prefetch_related`, migrations (`makemigrations`/`migrate`), `__str__`, admin registration + superuser.
- Days 12-13: Views, URLs, Templates — function & class-based views, `path()`/`include()`, template inheritance, Django Forms, static files.
- Day 14: Django Admin customization, fixtures, testing (`TestCase`, `client`, `assertContains`).

**Week 3 — Django REST Framework (DRF)** (Days 15-21)
- Days 15-16: Serializers — `ModelSerializer`, validation, nested serializers, `create()`/`update()`.
- Days 17-18: Views & ViewSets — `APIView`, `@api_view`, `GenericAPIView`, `ModelViewSet`, `ReadOnlyModelViewSet`, routers (`DefaultRouter`), URL registration.
- Days 19-20: Authentication & Permissions — `IsAuthenticated`, `IsAdminUser`, TokenAuth, SessionAuth, throttling classes.
- Day 21: Filtering, searching, pagination, custom permissions, Django CORS headers, API docs (drf-yasg / drf-spectacular) → Swagger UI.

**Week 4 — Testing, Security, Deployment** (Days 22-26)
- Days 22-23: Testing — DRF `APITestCase`, `APIRequestFactory`, `assertIn`, status codes; TDD workflow; pytest+pytest-django intro.
- Days 24-25: Production deployment — `gunicorn`, `whitenoise` (static), `psycopg2-binary`, `ALLOWED_HOSTS`, `DEBUG=False`, `.env`, `requirements_production.txt`, Dockerfile for Django, gunicorn systemd service sketch.
- Day 26: Projects + final assignment.

**Projects summary (Month 3)**
1. Python CLI Blog Engine (file-based JSON)
2. OOP Library Management System
3. Django Blog — models, admin, templates
4. Django REST API for Blog (CRUD)
5. DRF Todo API with Token Auth
6. Production-ready Django Notes API (Docker, gunicorn, tests)

**Assignments**
- Assignment 1: Build a Django REST API for a "Recipe Manager" (models: Recipe, Ingredient, Category; nested serializer; JWT or token auth; pagination; filtering by category; Swagger docs). Submission: repo, Postman collection, API docs screenshots.
- Assignment 2: Add testing & deployment — write ≥10 DRF tests; containerize with Docker; provide `.env.example` and `docker-compose.yml`; run `gunicorn` in production container; deploy to Railway/Render/Heroku free tier (or local via curl).

**Mini-Project file** `MINI-PROJECT-BLOG-API.md`: full Django+DRF Blog API — Overview, Features, Project Structure tree, Setup (venv, pip install -r, migrate, runserver, create superuser), Implementation per-file (settings, blog/models.py, blog/serializers.py, blog/views.py, blog/urls.py, project/urls.py, Dockerfile, docker-compose.yml, .env.example), Key Features, Learning Outcomes.

**Key Concepts Review** sections: Python, Django, DRF, Testing, Deployment — with ✅.

**Progress Checklist**: ~15 items mirroring Month 1/2 style.

**Next Steps**: link to Month 4.

---

## 2. Month 4 — Advanced Backend (FastAPI, Authentication, Async)

### Folder
`04-Month-4-Advanced-Backend/` → README.md (+ MINI-PROJECT-TASK-TRACKER.md)

### README.md outline (~1100–1300 lines)

**Learning objectives:**
- ✅ Master FastAPI async/await and dependency injection
- ✅ Design Pydantic models & validation
- ✅ Implement JWT & OAuth2 authentication
- ✅ Build secure APIs with middleware, CORS, rate limiting
- ✅ Apply async database access (SQLModel/asyncpg/SQLModel async session)
- ✅ Use background tasks & WebSockets
- ✅ Test FastAPI apps (pytest, HTTPX TestClient)
- ✅ Document APIs with automatic OpenAPI
- ✅ Containerize & deploy FastAPI (uvicorn, gunicorn workers, Docker)
- ✅ Build 5+ advanced backend projects

**Week 1 — FastAPI Fundamentals** (Days 1-6)
- Days 1-2: Intro — install, `main.py`, `@app.get`, path params (`{item_id}`), query params, request body with Pydantic `BaseModel` (`Field`, validators via `@field_validator`), response models (`response_model`), HTTP status codes, `FastAPI` vs `APIRouter`. Show interactive docs at `/docs`.
- Days 3-4: Dependency Injection — `Depends()`, `get_db` pattern, `OAuth2PasswordBearer` skeleton, sub-dependencies, `yield`-based deps (DB session teardown).
- Days 5-6: Pydantic deep — nested models, `Config`/`model_config`, `BaseSettings` for env, `EmailStr`/`constr`, `parse_obj`.

**Week 2 — Async Programming in Python** (Days 7-13)
- Days 7-9: `async`/`await`, `asyncio.sleep`, event loop concept, `asyncio.gather` vs `create_task`, `aiohttp`/`httpx` async HTTP clients, `async for` streams.
- Days 10-11: Async DB — `SQLModel` async engine/session, `async with session`, `select()`, `selectinload`; or `databases` library; asyncpg example.
- Days 12-13: Concurrency vs parallelism, thread pool executors, `run_in_threadpool`, avoiding blocking calls, testing async endpoints.

**Week 3 — Authentication & Security** (Days 14-20)
- Days 14-15: JWT — `python-jose`, create/access tokens, expiry, `OAuth2PasswordRequestForm`, tokenUrl, `HTTPException` for expired/invalid tokens.
- Days 16-17: OAuth2 (password flow), scopes, `Security()`, protected routes, password hashing (`passlib`/`bcrypt`).
- Days 18-19: Security hardening — CORS middleware, trusted host, HTTPS redirect, rate limiting (`slowapi`/`fastapi-limiter` + Redis), CSRF basics, Helmet-style security headers middleware.
- Day 20: Refresh tokens + logout (token blocklist), `Depends` security dependency pattern.

**Week 4 — Advanced Features, Testing & Deployment** (Days 21-26)
- Days 21-22: Background tasks, `BackgroundTasks` param, email/SMS mock; WebSockets (`WebSocketRoute`/`@app.websocket`), connection manager pattern; Server-Sent Events intro.
- Days 23-24: File upload (`UploadFile`, `python-multipart`), streaming responses, static files (`StaticFiles`), `RedirectResponse`/`FileResponse`.
- Day 25: Testing — `pytest` + `httpx.AsyncClient`/`TestClient`, `pytest-asyncio`, fixture DB override, mocking external calls.
- Day 26: Deployment — `uvicorn app.main:app --workers 4`, gunicorn uvicorn worker, Dockerfile with `python:3.11-slim`, `docker-compose.yml`, CORS prod config, deploy notes.

**Projects summary (Month 4)**
1. FastAPI Hello World + Pydantic CRUD (in-memory)
2. SQLModel Async Blog API (SQLite → Postgres)
3. JWT-secured Task API with roles
4. WebSocket Chat API
5. Background-jobs Notification API (file upload + email mock)
6. Production FastAPI service (Docker, tests, rate-limited, OpenAPI tagged)

**Assignments**
- Assignment 1: Real-time Task Tracker API — FastAPI + async SQLModel/Postgres, JWT auth with roles (admin/user), Pydantic validation, WebSocket live updates for task changes, pagination + filtering, automatic OpenAPI docs, 15 pytest tests.
- Assignment 2: Harden & deploy — add rate limiting + CORS config, refresh tokens, Dockerize with multi-stage build, `docker-compose` with Postgres + Redis, write `README` deploy steps; run locally with `httpx` smoke test.

**Mini-Project file** `MINI-PROJECT-TASK-TRACKER.md`: FastAPI Task Tracker — same template as Month 2 mini-project (Overview, Features, Structure tree, Setup, per-file Implementation: main.py, config.py, db.py, models, schemas, auth/security.py, deps, api routes, WebSocket manager, tests, Dockerfile, docker-compose.yml, .env.example), Key Features, Learning Outcomes.

**Key Concepts Review**: FastAPI, Async, Auth/Security, Testing, Deployment.
**Progress Checklist**: ~15 items.
**Next Steps**: link to Month 5 (note: build on FastAPI + Postgres → leads into DB/DevOps month).

---

## 3. Month 5 — Databases & DevOps (PostgreSQL, MongoDB, Docker, CI/CD)

### Folder
`05-Month-5-Databases-DevOps/` → README.md (+ MINI-PROJECT-CI-CD.md optional)

### README.md outline (~1200–1400 lines)

**Learning objectives:**
- ✅ Master PostgreSQL fundamentals & advanced queries
- ✅ Design normalized schemas & relationships
- ✅ Use MongoDB NoSQL document modeling
- ✅ Apply indexing & query optimization
- ✅ Containerize apps & databases with Docker
- ✅ Orchestrate multi-service stacks with Docker Compose
- ✅ Build CI/CD pipelines with GitHub Actions
- ✅ Deploy full-stack apps to AWS/Azure
- ✅ Configure Nginx, SSL, domain, monitoring
- ✅ Build 5+ DevOps/database projects

**Week 1 — PostgreSQL & Relational Modeling** (Days 1-6)
- Days 1-2: Install (Docker image `postgres:15`), psql basics, `\dt`, `\d`, CRUD SQL, data types, `SERIAL`/`UUID`, constraints (`PRIMARY KEY`, `UNIQUE`, `CHECK`, `FOREIGN KEY`).
- Days 3-4: Relationships & normalization — 1:1, 1:M, M:M join tables, normalization forms (1NF-3NF), `JOIN` (INNER/LEFT/RIGHT/FULL), `GROUP BY`, `HAVING`, aggregation (`COUNT/SUM/AVG`), subqueries.
- Days 5-6: Indexing — `INDEX`, `CREATE INDEX CONCURRENTLY`, `EXPLAIN`/`EXPLAIN ANALYZE`, query plan reading, partial indexes, Django/SQLAlchemy integration notes.

**Week 2 — MongoDB & NoSQL** (Days 7-13)
- Days 7-8: NoSQL concepts vs SQL, MongoDB Atlas setup, documents & collections, `mongo` shell basics, CRUD (`$set`, `$gt`, `$in`, `$regex`).
- Days 9-10: Schema design patterns (embedding vs referencing, 1:1/1:M/M:M), Mongoose-style with PyMongo/MongoEngine, `mongomock` for tests.
- Days 11-12: Aggregations `$match`/`$group`/`$lookup`/`$sort`, indexes, Atlas indexes & performance advisor, `ttl` indexes.
- Day 13: Transactions in MongoDB, change streams intro, choosing SQL vs NoSQL decision matrix.

**Week 3 — Docker & Containerization** (Days 14-20)
- Days 14-15: Images vs containers, `Dockerfile` instructions (`FROM`, `RUN`, `COPY`, `WORKDIR`, `CMD`/`ENTRYPOINT`, `.dockerignore`), layers, multi-stage builds.
- Days 16-17: Docker Compose — `docker-compose.yml` services (app, db, redis), networks, volumes, env_file, `depends_on`, scaling with `--scale`, `profiles`.
- Days 18-19: Volumes & persistence, `docker exec`, `docker logs`, `docker-compose up/down`, debugging containers, cleaning up (`docker system prune`).
- Day 20: Best practices — least-privilege user, healthchecks, build caching, `.dockerignore` for Python/Node.

**Week 4 — CI/CD & Cloud Deployment** (Days 21-26)
- Days 21-22: Git workflows (feature branch, PR), GitHub Actions basics — `workflow.yml`, jobs/steps, `actions/checkout`, setup-node/python, caching (`actions/cache`).
- Days 23-24: CI pipeline — linting, type-checking, tests on push, badge in README (Shields.io). CD pipeline — build & push Docker image to GHCR/AWS ECR, deploy triggers.
- Days 25-26: Cloud deployment — Linux basics refresher, Nginx as reverse proxy + static, Let's Encrypt SSL (`certbot`), domain/DNS, deploy Django/FastAPI to AWS EC2/AZURE App Service, PM2/gunicorn, env secrets. Monitoring/logging intro (health endpoint, basic logging to file).

**Projects summary (Month 5)**
1. PostgreSQL schema design & seed data script
2. PostgreSQL advanced queries & performance report
3. MongoDB blog API (PyMongo) with Atlas
4. Multi-service app in Docker Compose (frontend+api+postgres+mongo)
5. GitHub Actions CI/CD pipeline (lint+test+build) for a sample repo
6. Production deployment: Nginx + Docker + HTTPS on AWS/Azure (or local with self-signed)

**Assignments**
- Assignment 1: Database layer for a real project — design normalized PostgreSQL schema; seed + migration scripts; 10 optimized queries (incl. EXPLAIN ANALYZE output); MongoDB alternative for one entity; document when/why each DB chosen.
- Assignment 2: DevOps pipeline — full GitHub Actions workflow (lint, test with coverage, build & push Docker image, deploy to cloud or local nginx+https), `docker-compose.yml` with DBs, Nginx config, SSL setup notes; provide deploy verification checklist.

**Key Concepts Review**: PostgreSQL, MongoDB, Docker, CI/CD, Cloud — ✅ bullets.
**Progress Checklist**: ~15 items.
**Next Steps**: link to Month 6 (capstone, deploy the month-3/4/5 projects).

---

## 4. Month 6 — Capstone Projects & Deployment (Real-world applications)

### Folder
`06-Month-6-Capstone-Projects/` → README.md (+ mini-project/assignment detail)

### README.md outline (~1300–1500 lines)

**Learning objectives:**
- ✅ Architect & build real-world full-stack applications from scratch
- ✅ Apply system design & scalable architecture patterns
- ✅ Integrate frontend (React/Next.js), backend (Django/FastAPI), DBs
- ✅ Secure, test, optimize & deploy production applications
- ✅ Implement CI/CD, monitoring & error handling
- ✅ Polish & ship a professional portfolio
- ✅ Prepare for job interviews with project storytelling

**Week 1 — Project Planning & System Design** (Days 1-5)
- Days 1-2: Reading requirements, writing user stories, MVP vs scope, tech stack decision matrix (justify Django REST vs FastAPI, Postgres vs Mongo, React vs Next). Entity-Relationship diagrams; API design (OpenAPI).
- Days 3-4: Architecture patterns — layered/n-tier, clean architecture; DB design (relationships, indexing); folder structure; environment strategy (`.env`, settings module split).
- Day 5: Project 1 kick-off, planning doc template, CI/CD strategy, deployment target selection.

**Week 2 — Capstone Project #1: Full-Stack E-Commerce / Marketplace API** (Days 6-13)
- Build a backend (Django+DRF or FastAPI+SQLModel) with Postgres: Product catalog, Categories, Cart, Orders, Payments mock (Stripe test keys), JWT auth, permissions, rate limiting, pagination, filtering/searching, async tasks (Celery + Redis or FastAPI background tasks), tests, Swagger docs, Dockerfile, docker-compose, GitHub Actions CI/CD, Nginx + HTTPS deploy notes.
- Week 2 deliverables: working local API + tests ≥80% coverage + containerised.

**Week 3 — Capstone Project #2: Real-time SaaS / Social Dashboard (full-stack)** (Days 14-21)
- Frontend React/Next.js (from Months 1–2 skills) consuming the Month-6 APIs; state management (Redux/Context); routing; real-time via WebSocket; auth flow; responsive UI. Backend: FastAPI (async) or Django (channels for websockets); Postgres; MongoDB for activity feed; Redis pub/sub for real-time; tests; Docker; CI/CD; deploy.

**Week 4 — Deployment, Portfolio & Career Wrap-up** (Days 22-26)
- Days 22-23: Production deployment — domain, SSL (Let's Encrypt), Nginx reverse proxy, env secrets, monitoring (health endpoint, Sentry/logging), scaling notes, cost estimate on AWS/Azure. Docker Compose prod vs dev; DB backups; zero-downtime deploy.
- Days 24-25: Portfolio website v3 — showcase all 6 months' projects; project cards with live links, GitHub, tech stack; blog section; contact form; deployed on Vercel/Netlify/AWS S3+CloudFront.
- Day 26: GitHub profile README, resume/README for each project, interview-story cheat sheet (STAR), final progress validation.

**Capstone Projects summary**
1. Capstone #1: E-Commerce / Marketplace API (backend-focused, Month 6)
2. Capestone #2: Real-time SaaS Dashboard (full-stack, Month 6)
- Plus re-deployment of Month 3 Django Blog API, Month 4 Task Tracker API, Month 1/2 React apps to production with HTTPS.

**Assignments**
- Assignment 1: Ship Capstone #1 (E-Commerce API) to production — live URL, GitHub repo with CI/CD, Swagger docs, test suite, Postman collection, deployment write-up.
- Assignment 2: Ship Capstone #2 + Portfolio — full-stack real-time app deployed; professional portfolio site live; GitHub profile README; project READMEs updated; interview STAR stories for 3 projects.

**Mini-project / supporting files**: `MINI-PROJECT-ECOMMERCE-API.md` — complete E-Commerce API implementation (Overview, Features, Tech Stack, Project Structure tree, Setup, Implementation per-file: settings/env, ecommerce/ models (Product, Category, Cart, Order), serializers, views/viewsets, urls, auth (JWT), tasks (Celery), tests, Dockerfile, docker-compose.yml, .env.example, GitHub Actions workflow, Nginx config), Key Features, Learning Outcomes.

Also update root **README.md** repository structure block to reflect created folders (Months 3-6 now exist) — mark folders 07-12 as "future". (Note: editing README.md is allowed since it's updating the repo structure tree to match reality; the plan author treats docs as in-scope deliverables, not source code.)

**Key Concepts Review**: System Design, Backend, DevOps, Frontend Integration, Career Prep.
**Progress Checklist**: ~18 items (portfolio-focused).
**Next Steps**: link to Interview Preparation (future `07-Interview-Preparation`) & portfolio building; congratulatory message.

---

## 5. File Creation Summary (for implementing agent)

| Folder | Files to create | Primary tech |
|---|---|---|
| `03-Month-3-Backend-Basics/` | `README.md`, `MINI-PROJECT-BLOG-API.md` | Python, Django, DRF |
| `04-Month-4-Advanced-Backend/` | `README.md`, `MINI-PROJECT-TASK-TRACKER.md` | FastAPI, async, JWT |
| `05-Month-5-Databases-DevOps/` | `README.md` | PostgreSQL, MongoDB, Docker, CI/CD |
| `06-Month-6-Capstone-Projects/` | `README.md`, `MINI-PROJECT-ECOMMERCE-API.md` | Full-stack capstone, deployment |

**Root README.md**: update the `## 📂 Repository Structure` tree so Months 3-6 are no longer placeholders (they now have content) — optionally add a one-line note for 07-12 as future modules.

## 6. Quality Gates / Validation
- Each README ≥ 1100 lines, following exact H1→H2→objectives→weeks→projects→assignments→review→checklist→next-steps order.
- Code blocks labelled (`python`, `javascript`, `bash`, `yaml`, `sql`, `jsx`).
- Internal links to prior months and to next month at the end of each README.
- Mini-project files mirror Month 2's `MINI-PROJECT-TODO-APP.md` template.
- No secrets/credentials in examples (use `SECRET_KEY=your-secret-key-here`, `***` placeholders).
- Consistent emoji headers & footer style (`*Last Updated: June 2026*`).

## 7. Out of scope
- Folders 07-12 (Interview Preparation, DSA Roadmap, Portfolio Building, Freelancing Guide, Company Standards, Resources) — not requested; future work.
- Actual source code / runnable projects — documentation only.
