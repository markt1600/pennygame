# Family Room — Keep Them Alive!

A cozy canvas survival game with a global leaderboard.

## Run locally

Just open `index.html` in a browser. Without the backend, scores fall back to a personal leaderboard saved in your browser (localStorage).

## Deploy to Vercel (with global leaderboard)

1. Push this folder to a Git repo and import it in Vercel (or run `vercel` from this folder).
2. In your Vercel project: **Storage → Marketplace Database Providers → Upstash → Redis** (the free Hobby plan is fine). Connect it to the project — this auto-adds the `UPSTASH_REDIS_REST_URL` / `UPSTASH_REDIS_REST_TOKEN` (or `KV_REST_API_*`) environment variables. The API supports either naming.
3. Redeploy. The game will detect `/api/leaderboard` and switch from local scores to the shared global top-10.

## Scoring

Score = alive-seconds: every second, you earn 1 point per living family member. Keeping more people alive longer = more points.
