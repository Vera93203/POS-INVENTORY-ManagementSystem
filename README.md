# POS-INVENTORY-ManagementSystem

Point-of-sale and inventory management app (React + Express + Prisma).

## Run locally

**Prerequisites:** Node.js

1. Install dependencies: `npm install`
2. Copy `.env.example` to `.env` and configure as needed
3. Run the app: `npm run dev`

For Docker: `docker compose up`

## Deploy on Render

This repo includes a [Render Blueprint](https://render.com/docs/infrastructure-as-code) (`render.yaml`) for a single web service (Node + Express + React build).

### One-time setup

1. Install the [Render CLI](https://render.com/docs/cli): `brew install render`
2. Log in: `render login`
3. Push this repo to GitHub (already linked to [POS-INVENTORY-ManagementSystem](https://github.com/Vera93203/POS-INVENTORY-ManagementSystem)).

### Deploy via Dashboard (recommended)

1. Open [Render Dashboard](https://dashboard.render.com/) → **New** → **Blueprint**
2. Connect the GitHub repo `Vera93203/POS-INVENTORY-ManagementSystem`
3. Confirm `render.yaml` is detected → **Apply**
4. Optional: set `GEMINI_API_KEY` under the service **Environment** tab for AI insights

After deploy, open the service URL. Default login passwords: `admin123`, `manager123`, or `cashier123` (see app auth).

### Deploy via CLI

After `render login`, trigger a deploy from the linked service:

```bash
render services          # find service ID
render deploys create <service-id> --confirm --wait
```

Data under `data/` is stored on a 1 GB Render disk so inventory persists across restarts.
