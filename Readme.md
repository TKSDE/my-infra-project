# AWS Infrastructure and Kubernetes Deployment

This project provisions AWS infrastructure using Terraform and deploys applications to an EKS cluster using Helm charts.

## Project Structure

### Terraform Modules

- [VPC Module](./terraform/modules/vpc/)
- [EKS Module](./terraform/modules/eks/)
- [S3 Module](./terraform/modules/s3/)

### Terraform Environments

- [Production](./terraform/environments/production/)
- [Staging](./terraform/environments/staging/)

### Helm Charts

- [Next.js Website](./helm/charts/nextjs-website/)
- [React Dashboard](./helm/charts/react-dashboard/)
- [PostgreSQL Database](./helm/charts/postgresql/)
- [Redis Cache](./helm/charts/redis/)

## Setup Instructions

1. **Clone the repository**:
    ```bash
    git clone <repository-url>
    ```

2. **Navigate to the project directory**:
    ```bash
    cd project-root/
    ```

3. **Initialize and apply Terraform**:
    ```bash
    cd terraform/environments/production/
    terraform init
    terraform apply
    ```

4. **Deploy Helm Charts**:
    ```bash
    cd helm/charts/nextjs-website/
    helm install my-release .
    ```

### Notes

- Ensure all AWS credentials and secrets are securely stored in environment variables or AWS Secrets Manager.
