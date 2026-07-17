# PerceivIQ data dictionary (GitHub Pages)

Public, permanent host for the PerceivIQ interactive data dictionary.

**Live URL (after Pages is enabled):**  
`https://<your-github-user-or-org>.github.io/perceiviq-data-dictionary/`

## One-time setup

From this directory (after `gh auth login`):

```powershell
git init
git add .
git commit -m "Initial PerceivIQ data dictionary site"
gh repo create perceiviq-data-dictionary --public --source=. --remote=origin --push
gh pages --help 2>$null
```

Then in the GitHub UI:

1. Repo **Settings → Pages**
2. **Source:** Deploy from a branch
3. **Branch:** `main` / root (`/`)
4. Save

GitHub will publish at:

```text
https://<owner>.github.io/perceiviq-data-dictionary/
```

Share that URL with the client. It does not change when you update the file.

## Updating after dictionary edits

From the deliverables package:

```powershell
cd c:\Users\egeak\revelio-new\gopipelines\deliverables
.\scripts\publish_perceiviq_data_dictionary.ps1
```

Or with push:

```powershell
.\scripts\publish_perceiviq_data_dictionary.ps1 -Push
```

That overwrites `index.html` in this site repo from  
`docs/perceiviq_data_dictionary.html` and optionally commits + pushes.

## Notes

- Keep this repo **public** (or at least readable by the client) so the Pages link works without GitHub login.
- Do **not** put pipeline code or client credentials here — HTML dictionary only.
- `.nojekyll` tells GitHub Pages to serve the static HTML as-is.
