# Traderoom

Traderoom is a modern social web app for traders to:

- post daily trades
- share future trade ideas
- publish educational videos
- announce live sessions
- discuss using comments and likes

## Stack

- Next.js 16 (App Router, TypeScript)
- Prisma ORM
- SQLite (dev default, easy to swap to Postgres for production)
- NextAuth v5 (credentials auth + JWT sessions)
- Tailwind CSS v4
- Zod validation

## Social Feed Features

- Account-based posting, likes, and comments
- Feed-first home page with latest posts first
- Image and video upload directly in the post composer
- In-feed media rendering (image/video players)
- Optional external media URL support

## Local Setup

1. Install dependencies

```bash
npm install
```

2. Copy environment file

```bash
cp .env.example .env
```

3. Generate Prisma client and create DB schema

```bash
npm run prisma:generate
npm run prisma:push
```

4. Run the app

```bash
npm run dev
```

Open http://localhost:3000

## Production Notes

- Replace SQLite with Postgres by changing `DATABASE_URL`.
- Set a strong `AUTH_SECRET`.
- Run `npm run build` in CI.
- Apply DB backups and migration workflow before release.
- Enable HTTPS and secure cookie settings at deployment.
- Local uploads are saved to `public/uploads`; for cloud deployment, use object storage (S3/R2/Cloudinary) for persistent media.

## Scripts

- `npm run dev` - local dev
- `npm run lint` - lint checks
- `npm run build` - production build
- `npm run prisma:generate` - generate Prisma client
- `npm run prisma:push` - push schema to database
- `npm run db:studio` - inspect DB with Prisma Studio
