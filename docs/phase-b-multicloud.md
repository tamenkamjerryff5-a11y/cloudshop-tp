# Phase B2 — Week 4 (multi-cloud)

## Table

| Need | AWS | Azure | GCP |
|------|-----|-------|-----|
| VM | EC2 |Virtual Machines | Compute Engine |
| Object storage | S3 | Blob Storage|Cloud Storage |
| DNS | Route 53 |Azure DNS |Cloud DNS |
| CI | CodeBuild |Azure Pipelines |Cloud Build |

## Question

Why use **GitHub Actions** instead of installing Jenkins on your own VM? (5 lines)
GitHub Actions is a fully managed, serverless CI/CD platform that eliminates the operational overhead of provision-ing, patching, and scaling dedicated infrastructure. 
Unlike Jenkins, which requires manual VM administration, runtime upgrades, and security maintenance, GitHub Actions manages the execution environment automatically. 
It integrates natively into the source code repository, removing the need to configure webhooks or external access credentials manually. 
Workflows are defined cleanly as code inside the repository, allowing developers to scale concurrent builds instantly without resource bottlenecks. 
This dramatically lowers operational costs and shifts focus entirely toward building application features rather than managing deployment servers.
