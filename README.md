# Acquisition Backend Scaffold

An early Node.js backend scaffold using Express 5, Drizzle ORM, and Neon/PostgreSQL. The current source includes an HTTP entry point, a root route, a user schema, and database migration configuration. It does not yet implement a complete acquisition product or authenticated user workflow.

## Local setup

```bash
cp .env.example .env
npm ci
npm run dev
```

Configure your own database URL in `.env`. The current `development` database configuration expects a separate `neon-local` service; the example uses the remote-connection path. Inspect `src/config/database.js` before choosing a mode. Migration commands are `npm run db:generate` and `npm run db:migrate` and will affect the configured database.

The inherited package scripts also refer to Docker shell scripts and Jest that are not included in the current source; these are incomplete setup paths, not verified features.

## Provenance

Clean copy of [aarish-io/acquisition](https://github.com/aarish-io/acquisition), imported at the source owner's request. Credential-bearing local configuration and IDE records are excluded. See [PROVENANCE.md](PROVENANCE.md) for source commit and contributors. The original `package.json` declares ISC; no separate license file was present and no new license is asserted.
