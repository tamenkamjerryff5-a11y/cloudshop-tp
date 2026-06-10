# Phase A — Weeks 1 & 2

## 1. Cloud computing for CloudShop

(5 to 8 lines)

## 2. Classify as IaaS / PaaS / SaaS

| Service | Model (IaaS / PaaS / SaaS) | One sentence |
|---------|----------------------------|--------------|
| AWS EC2 |IaaS |You rent a virtual machine (server) in the cloud — you control the OS and software. |
| GitHub | PaaS| A managed platform to store, share and version your code without managing servers.|
| Docker Hub | PaaS|A managed registry to store and distribute Docker images without running your own registry. |
| Gmail | Saas|A ready-to-use email application delivered over the internet — no installation needed. |
| Your Flask API |Iaas |Your own application running on a rented VM; you manage everything from OS to code |
| GitHub Actions |Paas |a managed CI/CD automation service.You write the config, GitHub runs it for you |

## 3. Deployment model

- Why does CloudShop choose **public cloud**? (2 benefits, 1 risk)

— Cost efficiency: There is no need to buy servers. CloudShop pays only for the compute time it actually uses. A startup with limited budget benefits greatly from this.

 — Speed and scalability: The team can launch a server in under 2 minutes and scale up instantly during traffic peaks (e.g., Black Friday sales), without any manual hardware work.

 RISK— Data control: In a public cloud, data is stored on shared infrastructure managed by a third party (AWS). For a business handling sensitive customer data (addresses, payments), this creates compliance and privacy risks.
- Bank with internal datacenter: which model (public / private / hybrid)?


