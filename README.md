# Fullstack Template — Vite React + Tailwind v4 / Node TS + Mongo

[![Frontend CI](https://github.com/yolandaatt/Portfolio/actions/workflows/frontend.yml/badge.svg)](https://github.com/yolandaatt/Portfolio/actions/workflows/frontend.yml)
[![Backend CI](https://github.com/yolandaatt/Portfolio/actions/workflows/backend.yml/badge.svg)](https://github.com/yolandaatt/Portfolio/actions/workflows/backend.yml)

En snabbstartsmall för moderna projekt:

- **Frontend:** Vite + React + TypeScript + Tailwind **v4** (PostCSS v4), ESLint (flat), Prettier, Husky/lint-staged, **Vitest + Testing Library**
- **Backend:** Node 20 + Express + TypeScript + MongoDB (Mongoose), **Vitest + Supertest**, ESLint (flat), Prettier
- **CI:** separata GitHub Actions för client/server (lint, **test**, build)
- **Docker:** `docker-compose.dev.yml` (hot-reload) & `docker-compose.prod.yml` (Nginx + healthchecks)

---

## Innehåll

- [Krav](#krav)
- [Struktur](#struktur)
- [Använd som template](#använd-som-template)
- [Lokal utveckling (utan Docker)](#lokal-utveckling-utan-docker)
- [Utveckling med Docker Compose](#utveckling-med-docker-compose)
- [Produktion med Docker Compose](#produktion-med-docker-compose)
- [Miljövariabler](#miljövariabler)
- [Scripts](#scripts)
- [CI](#ci)
- [Editor & kodstil](#editor--kodstil)
- [Felsökning](#felsökning)
- [Licens](#licens)

---

## Krav

- **Node 20** (rekommenderat: `nvm use 20`)
- **npm 10+**
- **Docker Desktop** (för Compose-flöden)

---

## Struktur

```txt
.
├─ .github/workflows/
│  ├─ frontend.yml
│  └─ backend.yml
├─ .vscode/
│  ├─ settings.json
│  └─ extensions.json
├─ docker/
│  ├─ client.Dockerfile
│  └─ server.Dockerfile
├─ client/                    # Vite + React + TS + Tailwind v4
│  ├─ src/
│  │  ├─ App.tsx, main.tsx, index.css
│  │  └─ test/setup.ts        # jest-dom för Vitest
│  ├─ App.test.tsx            # exempeltest
│  ├─ vitest.config.ts
│  ├─ .env.example / .env / .env.production
│  ├─ postcss.config.js       # @tailwindcss/postcss
│  ├─ tailwind.config.ts
│  ├─ eslint.config.js / .prettierrc / .prettierignore / .husky
│  └─ nginx.conf              # används i client.Dockerfile (prod)
├─ server/                    # Express + TS + Mongo + Vitest
│  ├─ src/ (app.ts, index.ts, db.ts, routes/health.ts)
│  ├─ tests/health.test.ts
│  ├─ tsconfig.base.json / tsconfig.json / tsconfig.build.json
│  ├─ .env.example / .env
│  └─ eslint.config.js / vitest.config.ts
├─ docker-compose.dev.yml
├─ docker-compose.prod.yml
├─ .editorconfig
├─ .gitignore
└─ README.md
```
