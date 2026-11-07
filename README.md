# My hub

Your private hub repository. It deploys your [hub gateway](https://github.com/shelenhovskyi/hub-gateway) to your own Cloudflare account and keeps a history of every change.

- `hub.json` pins the gateway to an exact commit. The hub app proposes updates as pull requests that show the code diff; nothing changes until you merge.
- `.github/workflows/deploy.yml` deploys on every push to `main`, but only if every change since the last deploy came from you. Otherwise it stops and waits for you to run it by hand from the **Actions** tab.

## Secrets

Set by the hub app, encrypted in your browser before they reach GitHub:

| Secret | What it is |
|---|---|
| `CLOUDFLARE_API_TOKEN` | A Cloudflare API token from the "Edit Cloudflare Workers" template, limited to your account |
| `CLOUDFLARE_ACCOUNT_ID` | Your Cloudflare account ID |
| `ADMIN_TOKEN` | The token the hub app uses to talk to your gateway |

## First deploy

Open **Actions → deploy → Run workflow**. Running it by hand is how you approve a deploy.
