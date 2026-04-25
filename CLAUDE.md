# Dawn Everything3D

## Local preview

To preview changes locally before deploying:

```
shopify theme dev --theme 182678683950
```

This runs a local hot-reload server (usually at `http://127.0.0.1:9292`) that overlays your local file edits on top of the live theme's settings. It does **not** modify the live theme — it's safe for previewing. Use this instead of pushing to the live theme just to see how something looks.

## Deployment

Pushing to GitHub main is not enough to update the live website. The full deploy process is:

1. `git add <files> && git commit && git push origin main`
2. `shopify theme push --theme 182678683950 --allow-live`
3. `git pull origin main`

All three steps are required for changes to appear on the website. Step 3 is needed because Shopify writes back some changes after a push, so you must pull to stay in sync.

### Notes on `shopify theme push`

- Running `shopify theme push` without flags will prompt interactively and **fail** in non-interactive environments (like Claude Code). Always use the explicit flags.
- `--theme 182678683950` — the live theme ID for `dawn-everything3d/main`
- `--allow-live` — required to push directly to the live theme without an interactive confirmation prompt
- The live theme is `dawn-everything3d/main` (#182678683950). Other themes on the store are unpublished/dev and should not be used unless intentional.

### Theme list (for reference)

| Name | Role | ID |
|------|------|----|
| dawn-everything3d/main | live | 182678683950 |
| dawn-customized | unpublished | 182675505454 |
| Development (Apoorv's MacBook) | development | 185469731118 |
