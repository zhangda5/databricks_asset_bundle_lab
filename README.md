***Databricks Asset Bundle Lab***

**Introduction**

The Databricks Asset Bundle Lab repository provides a structured framework for deploying and managing Databricks assets-including jobs, notebooks, pipelines, and related resources-using the Asset Bundle approach. This approach allows teams to:

- Package multiple Databricks artifacts into a single deployable unit.
- Deploy consistently across multiple environments (development, testing, production).
- Automate deployment via CI/CD pipelines.
- Simplify environment-specific configuration, minimizing manual intervention.

This repository serves as a hands-on lab to demonstrate how to set up, deploy, and run Databricks Asset Bundles on Azure Databricks, enabling teams to adopt best practices for reproducible, scalable, and maintainable deployments.

Whether you are exploring Databricks automation for the first time or looking to streamline your CI/CD workflows, this lab provides a practical starting point with ready-to-use examples and step-by-step deployment instructions.

**Getting Started**

**Prerequisites**

- Access to an Azure Databricks workspace.
- Databricks CLI installed and configured.
- Appropriate workspace permissions to deploy jobs, pipelines, and other assets.

**Deploying the Asset Bundle**

- **Deploy to development:**
```
    databricks bundle deploy --target dev
```
- **Deploy to production:**
```
    databricks bundle deploy --target prod
```
- **Run a job or pipeline manually:**
```
    databricks bundle run
```
**Project Structure**

- databricks.yml - top-level configuration for the bundle.
- resources/ - job and pipeline definitions (YAML files).
- src/ - source code modules that get packaged and deployed.
- .github/workflows/ - CI/CD workflows for automated deployments.

**In this repo you'll find a simple project consisting of:**

This repository contains a simple end-to-end data pipeline that demonstrates the use of Databricks Asset Bundles for structured data processing across multiple layers:

- **Bronze Layer** - Raw parquet data files are ingested and stored in a bronze volume, organized into multiple tables.
- **Silver Layer** - Curated Delta tables are created in the silver layer.
- **Data Transformation** - Parquet data from the bronze layer is loaded and transformed into Delta format within the silver layer for further analysis or downstream processing.

**Next Steps & Recommendations**

- Inspect resources/ to understand job schedules, cluster configs, and dependencies.
- Customize scripts for user name, target workspace, conventions, authentication, and cluster settings.
- Use CI/CD automation (e.g., GitHub Actions) for consistent deployments.
- Maintain separate environments (dev, test, prod) to avoid accidental production changes.

**Useful Links**

- [What is the Databricks CLI? - Azure Databricks | Microsoft Learn](https://learn.microsoft.com/en-us/azure/databricks/dev-tools/cli/)
- [What are Databricks Asset Bundles? - Azure Databricks | Microsoft Learn](https://learn.microsoft.com/en-us/azure/databricks/dev-tools/bundles/)
- [GitHub Actions - Azure Databricks | Microsoft Learn](https://learn.microsoft.com/en-us/azure/databricks/dev-tools/ci-cd/github)
