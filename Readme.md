# AWS Infrastructure and Kubernetes Deployment

This project provisions AWS infrastructure using Terraform and deploys applications to an EKS cluster using Helm charts.

## Project Structure

### Terraform Modules

- **[VPC Module](./terraform/modules/vpc/)**: Defines the VPC resources.
- **[EKS Module](./terraform/modules/eks/)**: Manages the EKS cluster.
- **[S3 Module](./terraform/modules/s3/)**: Configures S3 buckets for storage.

### Terraform Environments

- **[Production](./terraform/environments/production/)**: Configuration for production environment.
- **[Staging](./terraform/environments/staging/)**: Configuration for staging environment.

### Helm Charts

- **[Next.js Website](./helm/charts/nextjs-website/)**: Helm chart for deploying the Next.js website.
- **[React Dashboard](./helm/charts/react-dashboard/)**: Helm chart for deploying the React dashboard.
- **[PostgreSQL Database](./helm/charts/postgresql/)**: Helm chart for PostgreSQL database deployment.
- **[Redis Cache](./helm/charts/redis/)**: Helm chart for Redis cache deployment.

## Setup Instructions

1. **Clone the repository**:
    ```bash
    git clone https://github.com/TKSDE/my-infra-project.git
    ```

2. **Navigate to the project directory**:
    ```bash
    cd my-infra-project/
    ```

3. **Initialize and apply Terraform**:

    **For the production environment**:
    ```bash
    cd terraform/environments/production/
    terraform init
    terraform apply
    ```

    **For the staging environment** (if applicable):
    ```bash
    cd ../staging/
    terraform init
    terraform apply
    ```

4. **Deploy Helm Charts**:

    **For the Next.js website**:
    ```bash
    cd ../../helm/charts/nextjs-website/
    helm install my-nextjs-release .
    ```

    **For the React Dashboard**:
    ```bash
    cd ../react-dashboard/
    helm install my-react-release .
    ```

    **For the PostgreSQL Database**:
    ```bash
    cd ../postgresql/
    helm install my-postgres-release .
    ```

    **For Redis Cache**:
    ```bash
    cd ../redis/
    helm install my-redis-release .
    ```

### Notes

- Ensure all AWS credentials and secrets are securely stored in environment variables or AWS Secrets Manager.
- Replace `my-nextjs-release`, `my-react-release`, `my-postgres-release`, and `my-redis-release` with appropriate release names based on your requirements.
- For additional configuration and customization, refer to the specific Helm chart `values.yaml` files and Terraform module documentation.