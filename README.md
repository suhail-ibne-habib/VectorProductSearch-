# Webay Inventory

Catalog + image-match API for the Webay N8N Messenger agent. Match customer photos to products and return product data with variants and Cloudinary gallery URLs.

## Docs

- [plan.md](plan.md) — goals, scope, work breakdown
- [stack.md](stack.md) — locked stack, architecture, API shapes
- [cursor.md](cursor.md) — short project pointer for agents

## Stack (locked)

Express + Prisma + PostgreSQL + pgvector; OpenCLIP in a Python embed worker; images on Cloudinary. No auth in v1.

## Layout

- `index.js` — API entrypoint
- `src/` — models, controllers, routes, services, config
- `embed/` — Python OpenCLIP worker (later)
- `docker-compose.yml` — `app` + `embed` + `postgres`

## Run

```bash
# copy env, then:
cp .env.example .env

# start API (Express wired in Part 3)
node index.js
# or
npm start
```

Docker Compose (full stack once later parts land):

```bash
docker compose up --build
```

API default: `http://localhost:8000`
# VectorProductSearch-
