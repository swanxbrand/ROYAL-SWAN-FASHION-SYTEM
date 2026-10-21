# Royal Swan Fashion Management

Private internal PWA for Royal Swan Fashion operations in Syokimau, Kenya.

## Stack
- React + TypeScript + Vite
- Express API with PostgreSQL via Prisma
- JWT-based authentication and role checks
- PWA manifest + service worker
- Optional public waiting list and pre-order pages

## Setup
1. Install Node.js 22 LTS.
2. Copy `.env.example` to `.env` and update values.
3. Create PostgreSQL database and run Prisma migrations.
4. Install dependencies: `npm install`
5. Run app: `npm run dev`
6. Production build: `npm run build`

## Environment
- `DATABASE_URL` points to PostgreSQL
- `JWT_SECRET` must be a strong secret
- `CLIENT_URL` is local origin for CORS
- `OWNER_EMAIL` and `OWNER_PASSWORD` are for the first owner bootstrap account

## Database
```bash
npm run db:generate
npm run db:migrate
npm run seed
```

## Security notes
- Never expose private employee dashboards publicly.
- All permission checks happen on the server.
- Private files are stored server-side and never cached in the app shell.
- Service worker caches only safe public shell assets, not private API responses.

## Launch window
The countdown uses the Africa/Nairobi timezone and the launch date is August 8, 2029.

## Deployment
- Deploy behind HTTPS.
- Use environment variables and secret managers.
- Keep PostgreSQL backups and rotate secrets regularly.
- Ensure only approved public pages are exposed.
