# Inkflow — Blog Platform

A Medium-inspired blog platform built with React, Express, PostgreSQL, and TypeScript.

## Quick Start

1. Copy env file and fill in values:
```bash
   cp .env.example .env
```
```env
   DATABASE_URL=your_postgres_connection_string
   SESSION_SECRET=any_random_secret_key
   NODE_ENV=development
```

2. Install, push schema, and run:
```bash
   npm install
   npm run db:push
   npm run dev
```

Server runs on `http://localhost:3000`

> Seed data auto-populates on first run — test accounts: `alice`, `bob`, `carol`, `dave` (password: `password123`)

## Stack

| Layer    | Tech                              |
|----------|-----------------------------------|
| Frontend | React + Vite + TailwindCSS + shadcn/ui |
| Backend  | Express.js + session auth         |
| Database | PostgreSQL + Drizzle ORM          |
| Routing  | wouter (client), Express (server) |

## Features

- Auth — register, login, session-based
- Articles — CRUD, drafts, rich reading view
- Social — claps, comments, bookmarks, follows
- Discovery — tags, search, trending, interest-based feed
- Onboarding — topic picker for new users
- UI — dark/light mode, responsive, animated

## Deployment (Vercel)

Add these environment variables in Vercel Dashboard → Settings → Environment Variables:
```
DATABASE_URL
SESSION_SECRET
NODE_ENV=production
```

## Security Highlights

- Passwords: SHA-512 with per-user salt + timing-safe comparison
- Sessions: `httpOnly`, `sameSite: lax`, `secure` in production
- Input validation on all routes
- Draft articles visible to author only