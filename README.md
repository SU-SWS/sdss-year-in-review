# SDSS Year in Review
[![Netlify Status](https://api.netlify.com/api/v1/badges/75eea7ad-1b69-4b19-a7a3-4c6c353892b9/deploy-status)](https://app.netlify.com/sites/sdss-year-in-review/deploys)

This repo contains a Netlify-hosted static website for SDSS's Year in Review. You can login to Netlify here: https://app.netlify.com/

- Netlify URL: https://sdss-year-in-review.netlify.app
- Live Stanford URL: https://sdss-year-in-review.stanford.edu/

This repo can host all Year in Review websites for each year in separate branches.

## Netlify Basics
- The Netlify site is directly connected to this repo through Github.
- When code is merged into the branch configured as the Netlify Production branch for the site, Netlify deploys the code to the live site.
- The active year's website branch is configured as the Netlify Production branch.
- The `/public` directory is where the static site files are.
    - The repo root is for Netlify configuration files.

### Making a new deployment
1. Fetch the latest code for the current active branch
1. Create a new branch for your changes
1. Make changes
    - If supplied with new site files don't copy them over the existing files in the branch -- wipe the `/public` directory and replace with new files.
1. After making changes, commit them, push up to repo, and create a PR.
    - Make sure the PR is set to merge into the active branch (it should be by default).
1. Netlify will run a few tests on the PR and also create a preview URL.
    - Wait for tests/checks to pass and then inspect/review the preview and verify it looks as intended.
1. Once the code is ready to deploy, squash and merge the PR into the active branch.
    - Whenever the active branch code is changed, it triggers a new deployment.

### Switch to a new site for the year
1. Create a branch for the year of the site (e.g., `2022-2023`)
1. Copy the `netlify.toml` and `lambda/.gitkeep` files from the most recent year's branch.
1. Create a new `/public` directory and copy the new site files in.
1. Push up the site.
1. When ready to launch, change the Production branch to the new year's branch in Netlify.
