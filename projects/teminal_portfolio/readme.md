# Terminal Portfolio Deployment (as Submodule)

This project demonstrates how to deploy a project (here, a terminal portfolio) that is included as a submodule in a monorepo to Azure Static Web Apps.

## Structure
- This repo contains the submodule folder: `ext_proj` (linked to https://github.com/AkashDas253/Terminal_Portfolio.git)

## Deployment Steps

1. **Push all changes to GitHub**
   - Ensure `.gitmodules`, the submodule folder, and all commits are pushed.

2. **Create Azure Static Web App**
   - In Azure Portal, create a new Static Web App.
   - Connect it to your GitHub repo and branch.

3. **Set Build Details**
   - **App location:** `ext_proj`
   - **Output location:** (depends on your app, e.g., `build` for React, or leave blank for static)
   - **API location:** (leave blank unless you have an API)

4. **Complete and Deploy**
   - Azure will build and deploy from the `ext_proj` folder.

## Keeping in Sync with the Submodule
- To update the submodule with the latest changes from the original repo:
  ```sh
  git submodule update --remote ext_proj
  git add ext_proj
  git commit -m "Update submodule to latest commit"
  git push
  ```
- Redeploy to Azure to reflect the latest changes.

## Notes
- You can also use the Azure Static Web Apps VS Code extension for deployment.
- This approach works for any subfolder/submodule in a monorepo.
