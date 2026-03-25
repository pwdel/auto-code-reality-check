# auto-code-reality-check

Static GitHub Pages microsite for the "Auto-Coding: Reality Check" presentation.

## Local preview

From this directory:

```sh
python3 -m http.server 8000
```

Then open `http://localhost:8000/`.

## GitHub Pages publish flow

This should be a project Pages site, so the repository name can stay:

`auto-code-reality-check`

Recommended remote creation flow:

```sh
gh repo create auto-code-reality-check --public --source=. --remote=origin --push
gh api --method POST /repos/pwdel/auto-code-reality-check/pages \
  -F source[branch]=main \
  -F source[path]=/
```

Expected Pages URL:

`https://pwdel.github.io/auto-code-reality-check/`

If the Pages site already exists, use `PUT` instead of `POST`:

```sh
gh api --method PUT /repos/pwdel/auto-code-reality-check/pages \
  -F source[branch]=main \
  -F source[path]=/
```
