# Data Guide deployment

1. Put this folder in a GitHub repository.
2. In Render choose **New > Blueprint** and select the repository. Render will read `render.yaml`.
3. When prompted, enter `OPENAI_API_KEY` as a secret. Do not commit `.env` or API keys.
4. Deploy. The web service uses `npm ci` and `npm start`, listens on `PORT`, and exposes `/api/health`.
5. The Render PostgreSQL service is wired to `DATABASE_URL`; `schema.sql` is applied automatically on startup.
6. Open the generated `https://data-guide-....onrender.com/` URL.
7. Optional custom domain: Render dashboard > service > Settings > Custom Domains.

## Local

Copy `.env.example` to `.env`, set credentials, then:

    npm install
    npm start

Open http://localhost:5000
