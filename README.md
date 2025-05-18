# DABs_Deplyment_With-Github-Action
Automated Deplyment with Github Action cover CI/CD pipelines. Adding ML Engeneering with DABs 

# Key Features:

Unified deployment of notebooks, jobs, clusters, and pipelines using DABs YAML configuration.

Automated testing and validation of code and infrastructure before deployment.

Version control integration for all source code, configuration, and assets.

Environment isolation (dev, test, prod) with parameterized settings.

Progressive deployment with automated rollbacks on failure.

databricks-dab-repo/
├── databricks.yml           # Bundle definition
├── resources/
│   ├── workflows/
│   │   ├── my_pipeline.yml  # Pipeline definition
│   │   └── my_pipeline_job.yml # Job definition
│   ├── clusters/
│   │   ├── dev_cluster.yml  # Dev cluster config
│   │   └── prod_cluster.yml # Prod cluster config
├── src/
│   ├── dlt_pipeline.ipynb   # Notebook(s)
│   └── mypython.py          # Python modules
└── README.md

# CI/CD Pipeline Overview
Development: Code and configuration changes are made locally or in a development workspace. Developers use version control (e.g., Git) for all files and assets.

Testing: On commit or merge, the CI/CD pipeline triggers automated tests (unit, integration) on Databricks using the Databricks CLI and frameworks like Nutter or pytest.

Deployment: If tests pass, the pipeline deploys the Databricks Asset Bundle to the target environment (dev/test/prod) using the CLI (databricks bundle deploy -t <env>).

Validation: The pipeline can run additional validation jobs using databricks bundle run -t <env> <job_name>.

Promotion: Upon successful validation, assets are promoted to production.
