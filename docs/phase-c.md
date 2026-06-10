# Phase C — Week 5 (DevOps pipeline)

## Your pipeline diagram

```
Local code → git push → GitHub Actions → tests → docker build
```

State: where does it **stop** if a test fails? What stays **manual** in your setup?
If a test fails, the pipeline execution *stops immediately at the "tests" stage* inside GitHub Actions, preventing the broken code from advancing to the "docker build" phase. In this lab setup, the final application deployment onto the actual server infrastructure remains completely *manual*.
## Questions

1. DevOps in one sentence:
DevOps in one sentence: DevOps is a collaborative mindset and engineering methodology that unifies software development (Dev) and IT operations (Ops) through automation, continuous integration, and continuous delivery to deliver high-quality software faster and more reliably.
2. Two measurable DevOps goals:
2. Two measurable DevOps goals:*
   * *Reduce Deployment Frequency (DF):* Increase how often successful code updates are safely released to production environments.
   * *Lower Mean Time to Repair (MTTR):* Decrease the average time required to diagnose, fix, and recover from a system failure or production outage.

3. What remains manual in **your** lab:
The actual provisioning of the underlying cloud host infrastructure (like EC2 instances or security groups) and the final steps of pulling and launching the newly built Docker container on the production host server must still be executed manually.

