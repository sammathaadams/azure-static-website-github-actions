# ☁️ Azure Static Website CI/CD

☁️ Azure | 🤖 GitHub Actions | 🚀 Automated Deployment

[![Deploy Azure Blob Static Website](https://github.com/sammathaadams/azure-static-website-github-actions/actions/workflows/deploy.yml/badge.svg)](https://github.com/sammathaadams/azure-static-website-github-actions/actions/workflows/deploy.yml) 

**Automated static website deployment to Azure Blob Storage using GitHub Actions.**
This project demonstrates moving from a manual Azure deployment to a fully automated CI/CD workflow where every push to the `main` branch updates the live website.

---

## 🎥  Watch Me Complete This Lab Here!

https://www.loom.com/share/944ce279b28144dba467a1863e020291

---

## 📌 Overview

This lab begins with a **manual deployment** of a static website to Azure Blob Storage and then introduces automation using GitHub Actions.

Project goals:

* Host a static website using Azure Storage Static Website
* Implement secure authentication with an Azure Service Principal
* Configure GitHub Actions Secrets
* Automate deployments using a push-to-deploy workflow

The repository itself contains the full implementation, including the GitHub Actions workflow and the website source files.

---

## 🏗️ Repository Architecture

```
Repository (AZURELABS)
│
├── Static-website/
│     ├── index.html
│     └── Sammatha_Adams_Resume.pdf
│
└── .github/workflows/
      └── deploy.yml   → CI/CD workflow
                          │
                          └── Deploys Static-website/ → Azure $web container
```

Key idea:

* `Static-website/` holds the site files.
* `.github/workflows/deploy.yml` controls automation.
* Pushing changes to `main` triggers deployment.

---

## ⚙️ Tech Stack

* Microsoft Azure Blob Storage (Static Website Hosting)
* Azure CLI
* GitHub Actions (CI/CD)
* GitHub Secrets
* HTML / CSS / JavaScript

---

## 🚀 Part 1 — Manual Deployment of Storage account

Before introducing automation, the website was deployed manually to Azure:

1. Created Storage Account `stlab01samm`
2. Enabled Static Website Hosting
3. Uploaded files into the `$web` container
4. Verified the public Azure endpoint

This manual deployment established the baseline environment used later by the pipeline.

---

## 🔐 Part 2 — Authorization Setup

Automation is secured using:

* Azure Service Principal authentication
* GitHub Actions repository secrets:

```
AZURE_CREDENTIALS
AZURE_STORAGE_KEY
```

These allow GitHub Actions to deploy updates without exposing personal credentials or requiring manual Azure login.

---

## 🤖 Part 3 — CI/CD Pipeline Intergration

Workflow location:

```
.github/workflows/deploy.yml
```

### Trigger

```
Push → main branch
```

### What the Pipeline Does

* Checks out repository code
* Authenticates to Azure using stored secrets
* Uploads files from `Static-website/`
* Updates the Azure `$web` container automatically

Because the workflow lives inside the repository, the full pipeline configuration can be viewed directly in the repo structure.

---

## 🧪 Part 4 — Testing the Pipeline

During the walkthrough, a small UI change is introduced to demonstrate automation in action.
### Demo Change (Deployment Indicator)

Add this snippet to `Static-website/index.html` (inside the `.container` div) to visibly confirm automated deployment:

```html
<p style="font-size: 0.8em; color:#888;">
  Deployed automatically via GitHub Actions CI/CD
</p>


Test process:

```bash
git add .
git commit -m "Test CI/CD deployment"
git push
```

After pushing:

1. GitHub Actions workflow starts automatically.
2. The pipeline deploys updated files to Azure.
3. Refreshing the live site shows the new change — no manual upload required.

---

## 🌐 Live Website

👉 *[(Check out My Website!)](https://stlab01samm.z13.web.core.windows.net/)*

---

## 👩🏽‍💻 Author

**Sammatha Adams**
Cloud | IT | Automation

GitHub: https://github.com/sammathaadams
LinkedIn: https://www.linkedin.com/in/sammatha-adams-746503152/
