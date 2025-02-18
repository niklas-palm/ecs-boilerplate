# ECS Boilerplate

Boilerplate for central ECS Cluster with decentralised creation of ECS services.

## Prerequisites

- Create ECR repo and replace the ECR repo variable in the `.github/workflows/app_build_deploy.yaml`
- Create API key and store in Secretmanager.

```bash
aws secretsmanager create-secret --name dev/platformdomain/api --secret-string '{"apikey": "INSERT YOUR KEY HERE"}'
```

> [!NOTE]  
> Note that the "default" values above, corresponds to the default ENVIRONMENT and NAMESPACE parameters in the cloudformation template. If you update the environment or the namespace in the template, make sure there's a corresponding api key in secretmanager.

## Usage

1. Deploy core infra

Update the

- stack variables in the `infra/makefile`
- the variables in the `.github/workflows/infra_deploy.yaml`

and check it in.

2. Build and deploy app

Same as above for

- stack variables in the `app/makefile`
- the variables in the `.github/workflows/app_build_deploy.yaml`

and check it in.
