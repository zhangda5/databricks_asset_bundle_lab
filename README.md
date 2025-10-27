# lab

Databricks Asset Bundle Lab
Introduction

The Databricks Asset Bundle Lab repository provides a structured framework for deploying and managing Databricks assets—including jobs, notebooks, pipelines, and related resources—using the Asset Bundle approach. This approach allows teams to:

Package multiple Databricks artifacts into a single deployable unit.

Deploy consistently across multiple environments (development, testing, production).

Automate deployment via CI/CD pipelines (e.g., GitHub Actions, Azure DevOps).

Simplify environment-specific configuration, minimizing manual intervention.

This repository serves as a hands-on lab to demonstrate how to set up, deploy, and run Databricks Asset Bundles on Azure Databricks, enabling teams to adopt best practices for reproducible, scalable, and maintainable deployments.

Whether you are exploring Databrick

## Getting started

1. Install the Databricks CLI from https://docs.databricks.com/dev-tools/cli/databricks-cli.html

2. Authenticate to your Databricks workspace, if you have not done so already:
    ```
    $ databricks configure
    ```

3. To deploy a development copy of this project, type:
    ```
    $ databricks bundle deploy --target dev
    ```
    (Note that "dev" is the default target, so the `--target` parameter
    is optional here.)

    This deploys everything that's defined for this project.
    For example, the default template would deploy a job called
    `[dev yourname] lab_job` to your workspace.
    You can find that job by opening your workpace and clicking on **Workflows**.

4. Similarly, to deploy a production copy, type:
   ```
   $ databricks bundle deploy --target prod
   ```

   Note that the default job from the template has a schedule that runs every day
   (defined in resources/lab.job.yml). The schedule
   is paused when deploying in development mode (see
   https://docs.databricks.com/dev-tools/bundles/deployment-modes.html).

5. To run a job or pipeline, use the "run" command:
   ```
   $ databricks bundle run
   ```
6. Optionally, install developer tools such as the Databricks extension for Visual Studio Code from
   https://docs.databricks.com/dev-tools/vscode-ext.html.

7. For documentation on the Databricks asset bundles format used
   for this project, and for CI/CD configuration, see
   https://docs.databricks.com/dev-tools/bundles/index.html.
