# Pre-Deployment Checklist

> **Student template:** build a checklist for this release before deployment. The headings guide your thinking; the checks themselves are yours to write.

## Release identity

- [ ] Confirm the version to be deployed: `v1.0.0`
- [ ] Confirm that the deployed commit is indeed the intended one on the `main` branch

## Target environment

- [ ] Confirm that the target environment is GitHub Pages (production)
- [ ] Verify that GitHub Pages is using deployment via GitHub Actions

## Access and prerequisites

- [ ] Verify write access to the repository and GitHub Actions workflows
- [ ] Verify that the deployment workflow exists at `.github/workflows/deploy.yml`
- [ ] Verify that the `main` branch contains the committed changes

## Files and configuration

- [ ] Verify the presence of `public/index.html`, `public/style.css`, and JavaScript files
- [ ] Verify that the workflow correctly publishes the `./public` folder
- [ ] Verify that file, script, and stylesheet paths are correct

## Security

- [ ] Verify that no passwords, tokens, or API keys are present in `public/`
- [ ] Confirm that `public/config.js` contains only visible, non-sensitive configuration

## Deployment readiness

- [ ] Verify that the site works locally by opening `public/index.html`
- [ ] Verify that the workflow triggers on a push to `main`

## Recovery readiness

- [ ] Verify that the commit currently in production is identified
- [ ] Verify that the rollback plan outlines how to revert to the last working version

## Post-deployment verification prepared

- [ ] Prepare to verify the GitHub Pages URL
- [ ] Prepare a test to load the page, CSS, and JavaScript
- [ ] Prepare a test for links and the main button's functionality

## Final decision

- Ready to deploy? **Yes / No**