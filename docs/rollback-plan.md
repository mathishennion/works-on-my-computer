# Rollback Plan

> **Student template:** decide how you would return to a known-good state if the new release is unacceptable.

## 1. Known-good state

- Known-good version: `v1.0.0`
- Commit / reference: `f508cca3204b56a148b749c1ec5532a859157e61`
- How was this state verified? The site loaded successfully on GitHub Pages, and the page, styling, JavaScript, links and responsive layout were checked.


## 2. Rollback triggers

What conditions would make you stop the new release and roll back?

- The deployed site does not load or returns errors.
- The page styling or JavaScript functionality is broken.
- A critical link or user workflow no longer works after deployment.

## 3. Decision responsibility

The release owner or the person responsible for the deployment decides whether to roll back. They should use the GitHub Actions logs, browser checks, the deployed site URL and the known-good commit as evidence.


## 4. Rollback prerequisites

What must be available before a rollback can be performed safely?

- Access to the repository and permission to push to `main`.
- The known-good commit or version: `v1.0.0`, commit `f508cca3204b56a148b749c1ec5532a859157e61`.
- The GitHub Pages URL and access to GitHub Actions deployment history.

## 5. Rollback procedure

| Step | Action | Expected result | Verification |
| --- | --- | --- | --- |
| 1 | Confirm the failure and record the deployed commit, URL and relevant GitHub Actions logs. | The rollback decision is supported by evidence. | Confirm the issue is reproducible in a browser. |
| 2 | Restore the known-good `v1.0.0` files from commit `f508cca3204b56a148b749c1ec5532a859157e61`. | The working tree contains the previously verified release. | Check the files in `public/` against the known-good commit. |
| 3 | Commit the rollback and push the change to `main`. | A new GitHub Actions deployment is triggered. | Confirm that the workflow starts in the Actions tab. |
| 4 | Wait for the workflow to upload `./public` and deploy it to GitHub Pages. | The known-good release is published. | Confirm that all workflow steps complete successfully. |
| 5 | Open the deployed application and run the recovery checks. | The application is usable again. | Complete the checks in section 6 and record the results. |

## 6. Verification after recovery

How will you prove that the rollback restored an acceptable state?

| Check | Expected result | Actual result | Pass / fail |
| --- | --- | --- | --- |
| GitHub Pages URL loads | The application homepage is displayed without an error. | To be recorded during the rollback. | Pending |
| Assets and JavaScript work | CSS is applied and the main application interaction works. | To be recorded during the rollback. | Pending |
| Links and responsive layout work | Links work and the page remains usable on supported screen sizes. | To be recorded during the rollback. | Pending |

## 7. Communication

Notify the release owner, the project owner and anyone testing or using the deployed application. Report the reason for the rollback, the affected release, the restored version, the deployment result and any remaining issues.


## 8. After the incident

What should be recorded or updated after the rollback?

- Record the incident, the evidence collected and the GitHub Actions workflow run.
- Record the restored commit and the results of the post-rollback checks.
- Update the deployment guide or runbook with the cause and any steps that would make recovery faster.

