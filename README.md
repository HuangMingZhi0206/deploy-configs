# deploy-configs

Compose files for the apps Coolify runs at home.

They live here, apart from the application repositories, for one reason: Coolify
reads `docker-compose.yml` straight from a Git repository at deploy time, so
that repository has to be readable without credentials. Keeping only these
files public lets the application repositories stay private.

Nothing secret is in here. A compose file names an image, a port, and the
*names* of environment variables — every value lives in Coolify.

| Folder | Coolify application | Built by |
|---|---|---|
| `portfolio/` | Portofolio Kevin Syonin | GitHub Actions in `PortfolioKSVercel` |
| `porto-angel/` | portfolio-aap-vercel | GitHub Actions in `portfolio-aap-vercel` |
| `angel/` | angel_birthday_20th | GitHub Actions in `angel_birthday_20th` (branch `master`) |

## Editing

Coolify does **not** re-read these files on every deploy. It keeps its own copy,
refreshed only when you press **Load compose** on the application. So after
changing anything here: Load compose, Save, Deploy.

Application code changes need none of that — they flow through Actions on their
own. This repository only matters when the shape of a deployment changes.
