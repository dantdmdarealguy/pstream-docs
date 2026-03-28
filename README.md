# P-Stream Docs

Documentation site for P-Stream, built with [Astro](https://astro.build) and [Starlight](https://starlight.astro.build).

## Development

```bash
pnpm install
pnpm dev
```

## Build

```bash
pnpm build
```

## Cloudflare Pages

Deploy directly from the Cloudflare Pages dashboard or via Wrangler CI:

| Setting | Value |
|---------|-------|
| **Build command** | `pnpm install && pnpm build` |
| **Build output directory** | `dist` |

**Environment variables to set in the Cloudflare Pages dashboard:**

| Variable | Value | Description |
|----------|-------|-------------|
| `SITE_URL` | `https://your-project.pages.dev` | Your Cloudflare Pages domain (or custom domain) |
| `BASE_PATH` | `/` | Site is served at the root — no subdirectory needed |
| `NODE_VERSION` | `20` | Ensures a modern Node.js is used during the build |
| `PNPM_VERSION` | `10` | Matches the `pnpm@10.x` version declared in `package.json` |

> **Note**: `SITE_URL` and `BASE_PATH` are consumed at **build time** by `astro.config.mjs` —
> they are not needed at runtime.

## Docker

Build and run with Docker:

```bash
docker build -t mov-docs .
docker run -p 8080:8080 mov-docs
```

Or use Docker Compose:

```bash
docker compose up
```

The container image is also available at [ghcr.io/okikio/mov-docs](https://ghcr.io/okikio/mov-docs).

## Environment Variables

| Variable | Default | Description |
|----------|---------|-------------|
| `SITE_URL` | `https://okikio.github.io` | The base site URL for the build |
| `BASE_PATH` | `/mov-docs` | The base path for the site |
| `PORT` | `8080` | Port for the Docker container |
