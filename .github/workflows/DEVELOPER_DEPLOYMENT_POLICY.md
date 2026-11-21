# Developer Hosting Deployment Policy

**Version:** 1.0  
**Effective date:** 20 November 2026

## 1. Purpose

This document explains how developer projects are deployed to their assigned subdomains, what developers are expected to do, and which actions may result in deployment access being suspended or removed.

This is an operational policy for use of the hosting deployment service. The administrator may update it and will notify developers of material changes.

## 2. How deployment works

1. The developer maintains the project in the GitHub repository assigned by the administrator.
2. A push to the repository's `main` branch starts the deployment request workflow.
3. The administrator's GitHub repository checks that the project ID is approved and reads the specified commit from the developer repository.
4. GitHub Actions uploads eligible repository files to the developer's assigned subdomain folder in cPanel hostig.
5. Files with matching names are replaced by the uploaded versions. New folders and files are added where possible.

The deployment destination is controlled by the administrator. Developers cannot choose or change server paths through their repository. cPanel credentials and API tokens are kept in the administrator's GitHub repository and must never be requested or shared with developers.

## 3. Developer responsibilities

Developers must:

- Use only the GitHub repository, project ID, and subdomain assigned to them.
- Keep deployable website files in the repository root (`./`) or in folders beneath it.
- Push approved changes to `main` when ready to deploy.
- Keep the deployment workflow and its `DEPLOY_TRIGGER_TOKEN` secret private and unchanged unless the administrator requests a change.
- Keep the project buildable and usable on the hosting service's supported runtime. This deployment uploads repository files; it does not install packages or run a build command.
- Ensure that required production files are committed. The workflow excludes `node_modules`, so dependencies must not rely on that folder being uploaded.
- Report failed deployments to the administrator with the GitHub Actions run link and the relevant error. Never include secret values in reports.
- Test changes on the assigned subdomain after a successful deployment.

## 4. Files excluded from hosting

The deployment workflow skips common development and private files, including:

- `.git/`, `.github/`, and `node_modules/`
- `.env*` files
- `.cpanel.yml`
- `.gitignore`, `.gitattributes`, and `.editorconfig`
- `README.md`, `LICENSE`, `CHANGELOG.md`, and `CONTRIBUTING.md`
- `.DS_Store` and `Thumbs.db`

Do not use the hosting deployment to publish environment files, credentials, private keys, access tokens, database passwords, or other confidential information. The exclusions are safeguards; they are not permission to commit secrets to GitHub.

## 5. Prohibited actions

Developers must not:

- Change the assigned project ID (repository name) to request deployment of another developer's project.
- Attempt to alter, bypass, or discover another project's destination path or files.
- Add cPanel credentials, API tokens, FTP passwords, private keys, or production `.env` files to the repository.
- Add scripts or workflow steps intended to expose secrets, access another project, damage hosting files, or bypass administrator controls.
- Upload malware, phishing pages, unlawful material, content that infringes another party's rights, or content that harms the hosting service or other users.
- Use the assigned subdomain for spam, unauthorized data collection, attacks, proxying, cryptocurrency mining, or unrelated services.
- Deploy changes that knowingly disrupt other projects or shared hosting services.

  If you disobay one of the prohibition or mis use the service you will lost the access to the service

## 6. Deployment behavior and limitations

- The workflow uploads files from the repository root, subject to the exclusions above.
- A same-named file is intended to be overwritten by the latest deployment.
- New folders are created when needed. If cPanel rejects a file or folder operation, the deployment fails and the Actions log should be shared with the administrator.
- Files deleted or renamed in GitHub are **not automatically deleted** from hosting by the current workflow. Ask the administrator to review and remove stale files safely.
- A successful request in the developer repository only means the admin deployment was triggered. Confirm that the separate deployment run in the administrator repository completed successfully.
- The administrator may pause a deployment while investigating errors, security concerns, or conflicts with the assigned subdomain.

## 7. Suspension or loss of deployment access

The administrator may pause or remove a developer's deployment access if the developer:

- Attempts to access or deploy to another project's files or destination.
- Exposes, shares, or misuses deployment secrets or tokens.
- Deliberately bypasses the deployment restrictions or changes the workflow to cause unauthorized actions.
- Publishes malware, phishing, unlawful content, or material that creates a serious security or service risk.
- Repeatedly deploys changes that damage the assigned site or disrupt other hosting users.
- Uses the hosting service for spam, attacks, unauthorized data collection, or unrelated resource-intensive activity.
- Loses authorization to the assigned repository or no longer has approval to use the hosting service.

Where practical, the administrator will identify the issue and allow it to be corrected. Serious or active security risks may require immediate suspension. Access may be restored after the administrator verifies that the issue is resolved.

## 8. Acknowledgment

By using the deployment workflow, the developer confirms that they have read and will follow this policy. Questions or requests for a new project ID, subdomain, or cleanup of obsolete files must be sent to the administrator.

`Whatsapp: +255 715 874 294`

`Email: saidmnuby@gmail.com`

visit: https://techwaretz.elimutaifa.co.tz
