# README

This starting point uses Vite+React for the frontend, Express.js for the backend with Drizzle as an ORM+DB migration handler.

## Set Up

Start the postgres database in docker with:

```bash
docker compose up -d
```

The user and password are both postgres, the database name is `weird_salads_javascript_development`, and it's listening on port 6679 (to try avoid conflict in case you have another postgres server running). In short:

```bash
postgresql://postgres:postgres@localhost:6679/weird_salads_javascript_development
```

Install dependencies and start serving the backend:

```bash
# In the same directory as this README
cd backend
npm install
npm run dev
```

The backend should now be listening on http://localhost:3000/, and can leave this running while you develop, as it'll autoload any changes you make. For details on the backend, see the [express js docs](https://expressjs.com/).

Next, set up the frontend (in another terminal):

```bash
# In the same directory as this README
cd frontend
npm install
npm run dev
```

You should now be able to reach the frontend on http://localhost:5173. If you're not seeing data in the staff table, make sure you've still got the backend running.

## Adding models

Add your model in `backend/drizzle/schema/`, following the staff example or the [drizzle docs](https://orm.drizzle.team/docs/get-started/postgresql-new#step-4---create-a-table).

You can then generate and run a migration with:

```bash
npx drizzle-kit generate
npx drizzle-kit migrate
```

## Placeholder view

You'll find a placeholder view using the Staff model, which serves only as an example. Feel free to delete, modify, expand, or do whatever else you like with it.

## What next?

Up to you! Refer back to the briefing doc.

Feel free to replace or extend this README or add a separate documentation file of your own for your notes.
