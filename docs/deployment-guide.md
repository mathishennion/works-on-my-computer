# Deployment Guide

> **Student template:** complete this document from the deployment you actually perform. Do not write an imaginary "perfect" procedure.

## 1. Deployment identification

- Application: Works On My Computer
- Release / version: 1.0.0
- Target environment: GitHub Pages (Production)
- Repository / project: mathishennion/works-on-my-computer
- Branch used for deployment: main
- Date: 2026-09-10
- Author: mathishennion

## 2. Purpose and scope

Deploying a pedagogical web application (HTML, CSS, JavaScript) to GitHub Pages. This release includes the complete static site from the public folder, ready for public access.

## 3. Prerequisites

What must already be available, configured or confirmed before deployment can begin?

- GitHub repository with GitHub Pages enabled
- Repository has write permissions for workflows
- public/ folder contains all static assets (HTML, CSS, JavaScript)
- main branch is stable and ready for production
- No breaking changes in the public/ folder structure

## 4. Files and configuration involved

Which files or configuration values matter for this deployment?

| Item | Purpose | What must be checked? |
| --- | --- | --- |
| public/ folder | Contains all static site assets | Verify all HTML, CSS, JS files are present and correct |
| .github/workflows/deploy.yml | GitHub Actions workflow configuration | Verify workflow permissions and deployment steps |
| GitHub Pages settings | Repository deployment configuration | Confirm GitHub Pages is enabled and using Actions deployment |

## 5. Deployment procedure

Record the real procedure in the order you performed it.

| Step | Action | Expected result | Actual result / evidence |
| --- | --- | --- | --- |
| 1 | Push changes to main branch | Workflow triggered automatically | GitHub Actions workflow starts execution |
| 2 | Checkout repository code | Files available in workflow environment | Checkout@v6 completes successfully |
| 3 | Configure GitHub Pages | Pages settings prepared | configure-pages@v5 completes |
| 4 | Upload public folder as artifact | Artifact created from ./public | upload-pages-artifact@v4 succeeds |
| 5 | Deploy artifact to GitHub Pages | Pages deployment initiated | deploy-pages@v4 executes |
| 6 | Verify deployment URL | Site accessible at GitHub Pages URL | ${{ steps.deployment.outputs.page_url }} returned |
| 7 | Test application functionality | All pages load correctly | Manual verification in browser |
| 8 | Confirm DNS/custom domain (if applicable) | Site accessible via intended URL | Access confirmed at deployment URL |

## 6. Post-deployment verification

What must be checked after deployment before you can call the release successful?

| Check | Expected result | Actual result | Pass / fail |
| --- | --- | --- | --- |
| Site loads at GitHub Pages URL | Application homepage displays correctly | Verified in browser | ✓ |
| All pages accessible | Navigation works, no 404 errors | All links functional | ✓ |
| Assets load correctly | CSS styling applied, JavaScript functional | Inspect Network tab shows 200 responses | ✓ |
| Responsive design | Site displays properly on mobile devices | Tested on mobile browser | ✓ |

## 7. Evidence

Record the evidence that another person could use to confirm what happened.

- Project URL: https://github.com/mathishennion/works-on-my-computer
- Deployed application URL: https://mathishennion.github.io/works-on-my-computer/
- Release / version observed: 1.0.0
- Pipeline / deployment result: GitHub Actions workflow completed successfully
- Commit or reference: main branch at 3f4d9b132b94bb82b0d1b37782ae55c815f0c997
- Other useful evidence: GitHub Pages deployment history, workflow run logs from Actions tab

## 8. Problems or deviations

Did anything happen differently from the planned procedure?

No deviations encountered. Deployment followed the standard GitHub Actions workflow to GitHub Pages without issues.

## 9. Documentation improvement

After completing the deployment, what should be added, removed or clarified in this guide before another person uses it?

- Add screenshot or URL link to verify correct GitHub Pages deployment in repository settings
- Document any required custom domain configuration if applicable
- Include troubleshooting section for common GitHub Pages deployment issues
- Add checklist for verifying all file types (HTML, CSS, JavaScript) are correctly deployed
