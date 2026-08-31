# CLAUDE.md — varrd

## ⭐ How We Ship — SDLC etiquette (READ BEFORE ANY COMMIT)

> Canonical rules: `docs/SDLC.md` in `varrdinc/_VARRD_`. The non-negotiables:
>
> - **Never push to `main`** (org ruleset blocks it). Branch (`claude/<desc>`) → PR →
>   review → squash-merge. Default approver: **@augiemazza** (see CODEOWNERS).
> - **Never `git add -A`.** Stage ONLY files you changed, by name.
> - PR body = **root cause · fix · risk · how tested**.
> - One logical change per PR. Branches auto-delete on merge.
> - Never force-push `main`, never `--no-verify`.
> - **Never commit a secret** (key, token, password, .env). Secrets live in AWS SSM
>   Parameter Store under `/varrd/*` — reference by name, fetch at runtime.
> - Found gross/outdated code while working? Fix it in its OWN small PR — never smuggled.
