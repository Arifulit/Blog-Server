
# Next Blog Server

A modular REST API backend for a blog platform, built with TypeScript, Express, and Prisma.

## Overview

This project provides a clean server-side foundation for blog applications with:

- User management APIs (create, read, update, delete)
- Post creation API with user relation
- Prisma ORM integration
- Type-safe TypeScript codebase
- Ready-to-import Postman collection

## Tech Stack

- Node.js
- TypeScript
- Express.js
- Prisma ORM
- PostgreSQL (via Prisma datasource)
- ts-node-dev

## Project Structure

```text
next-blog-server/
|- prisma/
|  |- schema.prisma
|  |- migrations/
|- src/
|  |- app.ts
|  |- server.ts
|  |- config/
|  |  |- db.ts
|  |- modules/
|     |- user/
|     |  |- user.contoller.ts
|     |  |- user.routes.ts
|     |  |- user.service.ts
|     |- post/
|        |- post.controller.ts
|        |- post.router.ts
|        |- post.service.ts
|- next-blog-server.postman_collection.json
|- package.json
|- tsconfig.json
```

## Environment Variables

Create a `.env` file in the project root and set the following values:

```env
PORT=3000
NODE_ENV=development
DATABASE_URL=postgresql://USER:PASSWORD@HOST:PORT/DATABASE
```

## Getting Started

1. Install dependencies:

```bash
npm install
```

2. Generate Prisma client:

```bash
npx prisma generate
```

3. Run migrations:

```bash
npx prisma migrate dev
```

4. Start development server:

```bash
npm run dev
```

Server default URL:

```text
http://localhost:3000
```

## Available Scripts

```bash
# Development
npm run dev

# TypeScript build
npm run build

# Production start
npm run start
```

## API Endpoints

Base URL: `/api/v1`

### User

- `POST /user` - Create user
- `GET /user` - Get all users
- `GET /user/:id` - Get user by id
- `PATCH /user/:id` - Update user
- `DELETE /user/:id` - Delete user

### Post

- `POST /post` - Create post

### Health Check

- `GET /` - Returns `API is running`

## Postman Collection

Use the ready collection file:

- `next-blog-server.postman_collection.json`

Import this file in Postman and set `baseUrl` as needed.

## Common Troubleshooting

### Error: `Cannot find module '.prisma/client/default'`

Run:

```bash
npx prisma generate
```

If the problem persists, ensure:

- `DATABASE_URL` is present in `.env`
- Prisma packages are installed correctly
- Your Prisma schema configuration matches the installed Prisma version

## Author

Next Level Web Development