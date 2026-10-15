# Acquisition · Backend Foundation

An early backend project establishing an Express application, a PostgreSQL user schema, and a Drizzle migration workflow. Its current scope is infrastructure setup rather than a complete acquisition-management product.

**Node.js · Express 5 · Drizzle ORM · Neon/PostgreSQL**

[Portfolio](https://github.com/kuvlay)

## Current implementation

- Express server with a root health-style response.
- Environment loading and configurable server port.
- User schema containing name, unique email, password, role, and timestamps.
- Neon database adapter and Drizzle schema/migration configuration.
- ESLint and Prettier configuration.

The user table is a schema definition; registration, password hashing, login, and user-management endpoints are not implemented yet.

## Run locally

```bash
git clone https://github.com/kuvlay/acquisition.git
cd acquisition
cp .env.example .env
npm ci
npm run dev
```

The root endpoint is `http://localhost:3000/` by default. Set `PORT` to change it.

| Variable | Purpose |
| --- | --- |
| `PORT` | Express listening port |
| `DATABASE_URL` | Your PostgreSQL/Neon connection string |
| `NODE_ENV` | Selects database connection behavior |

The current database adapter routes `NODE_ENV=development` to a separately managed `neon-local` service. The example configuration uses the remote Neon path. Configure your own database before running any migration command.

## Development commands

```bash
npm run lint
npm run format:check
npm run db:generate
npm run db:migrate
```

`db:generate` creates migration files; `db:migrate` applies them to the configured database. `db:studio` opens Drizzle Studio.

## Status

This is a backend scaffold. The inherited Docker commands refer to shell scripts that are not present, and the test command refers to Jest without an installed Jest dependency. Those setup paths remain incomplete. No local runtime, migration, or test result is claimed by this documentation update.

<details>
<summary>Credits and project history</summary>

Clean source copy of [aarish-io/acquisition](https://github.com/aarish-io/acquisition). Local credentials and IDE records are excluded, and templates contain placeholders. [PROVENANCE.md](PROVENANCE.md) records the source commit and contributors. The original package manifest declares ISC; no additional license is granted here.

</details>
