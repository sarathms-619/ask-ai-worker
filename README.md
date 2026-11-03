# Ask AI Worker

The "Ask Sarath's AI" chat on sarathms.com.

Everything the bot knows lives in `SYSTEM_PROMPT` inside `worker.js`. Edit that text and push:
Cloudflare redeploys automatically (Workers & Pages → `sarath-digital-twin` → Settings → Build,
connected to this repo, root directory `/`).

- The `CLAUDE_KEY` secret is stored in Cloudflare, never in this repo.
- Chats and captured emails go to the `sarath-twin-db` D1 database (`chat_logs`, `leads`).
- If the bot can't reach Claude, the real error is saved in `chat_logs.ai_response` as `[error] ...`.

Deploy by hand instead:

```bash
npx wrangler deploy
```
