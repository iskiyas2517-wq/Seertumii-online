# Seertumii Online Backend + Android project

This version replaces SQLite with PostgreSQL so the database can persist on a hosted service.

## Deploy backend
Use a Node.js host that supports PostgreSQL. For Render, the included `render.yaml` creates a web service and PostgreSQL database.

Set these environment variables:
- `DATABASE_URL` = PostgreSQL connection string
- `JWT_SECRET` = long random secret
- `PORT` is supplied by the host

After deployment, test:
`https://YOUR-SERVICE-DOMAIN/api/health`

## Build web client
From `client`:
`npm install`
`VITE_API_URL=https://YOUR-SERVICE-DOMAIN npm run build -- --base ./`

For Windows PowerShell:
`$env:VITE_API_URL='https://YOUR-SERVICE-DOMAIN'; npm run build -- --base ./`

## Capacitor Android
From `mobile`:
`npm install`
`npx cap add android`
`npx cap sync android`
`npx cap open android`

Then Android Studio: Build > Build APK(s).

## Important
This is a prototype reward/withdrawal system. It does not transfer real money. Before real payouts, implement provider integration, KYC/age requirements, fraud prevention, rate limiting, audit logs, secure secrets, privacy policy, terms, and applicable local legal/compliance review.
