# Deploying to GitHub Pages Using GitHub Actions

This document describes the steps taken to deploy the CSS Framework
Comparison project to GitHub Pages using GitHub Actions.

## 1. Create GitHub Actions Workflow

A workflow file was created in:

.github/workflows/deploy.yml

This workflow:

-   Runs on every push to the main branch
-   Installs Node.js
-   Installs dependencies inside the sass-bulma directory
-   Builds Sass to CSS
-   Uploads the site as a GitHub Pages artifact
-   Deploys using actions/deploy-pages@v4

Key configuration sections include:

Trigger on push to main:

on: push: branches: - main

Required permissions:

permissions: contents: read pages: write id-token: write

Deployment step:

-   uses: actions/deploy-pages@v4

## 2. Enable GitHub Pages in Repository Settings

GitHub Pages must be enabled manually in the repository settings.

Steps:

1.  Go to Repository -\> Settings
2.  Click Pages
3.  Under Build and deployment
4.  Set Source to: GitHub Actions

If this step is skipped, deployment fails with errors such as:

HttpError: Not Found Get Pages site failed

## 3. Add a .gitignore File

Initially, no .gitignore file was present.

A .gitignore file was added to prevent unnecessary files from being
committed, especially node_modules.

Content of .gitignore:

node_modules/ sass-bulma/node_modules/ .DS_Store

This ensures:

-   node_modules is not uploaded
-   The repository stays clean
-   The GitHub Pages artifact remains small

## 4. Remove node_modules from Git Tracking (If Necessary)

If node_modules was previously committed, it must be removed from Git
tracking using:

git rm -r --cached sass-bulma/node_modules git commit -m "Remove
node_modules from repo" git push

## 5. Build Process

The workflow performs the following steps:

1.  Installs dependencies in sass-bulma

2.  Runs the build script:

    npm run build:css

3.  Uploads the repository as a GitHub Pages artifact

4.  Deploys the artifact to GitHub Pages

## 6. Live Website URL

After a successful workflow run, the site becomes available at:

https://nilma.github.io/css-framework-comparison/

The link can be found in:

-   Settings -\> Pages
-   Or Actions -\> Latest workflow run -\> Deploy job

## Final Result

After:

-   Creating the workflow
-   Adding .gitignore
-   Enabling GitHub Pages (GitHub Actions)
-   Pushing changes to main

The GitHub Actions workflow runs successfully and deploys the site
automatically on every push to the main branch.
