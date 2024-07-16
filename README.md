# Setup

- Make `.env`

  ```
    # Backend application port
    PORT=3000

    # Notice that we do not need superuser credential anymore.
    POSTGRES_DB=mydb
    POSTGRES_PORT=5432
    POSTGRES_HOST=localhost
    POSTGRES_APP_USER=appuser
    POSTGRES_APP_PASSWORD=1234
  ```

- `npm i`

# Sync database

- Pushing

  - `npm run db:push`

- Migrating `recon log`
  - `npm run db:generate`
  - `npm run db:migrate`

# Dev operations

- Start dev
  - `npm run dev`
- Build
  - `npm run build`
- Start production
  - `npm run start`

# Containerization and test

- Make `.env.test`

  ```
    # Backend application port
    PORT=3000

    # Notice that we do not need superuser credential anymore.
    POSTGRES_DB=mydb
    POSTGRES_PORT=5432
    POSTGRES_HOST=pf-db # Notice that we use the container name here.
    POSTGRES_APP_USER=appuser
    POSTGRES_APP_PASSWORD=1234
  ```

- `docker compose --env-file ./.env.test up -d --force-recreate --build`

# Push to dockerhub

- `docker tag preflight-backend [DOCKERHUB_ACCOUNT]/preflight-backend:latest`
- `docker push [DOCKERHUB_ACCOUNT]/preflight-backend:latest`
