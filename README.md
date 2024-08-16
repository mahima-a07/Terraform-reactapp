# Terraform EKS Cluster Setup

This repository contains Terraform configuration files for setting up an Amazon EKS cluster along with a VPC, security groups, and necessary outputs. The following files are included:

- `eks-cluster.tf`: Manages the EKS cluster and associated resources.
- `outputs.tf`: Defines the output values such as the cluster endpoint and security group ID.
- `security-group.tf`: Configures security groups for the EKS cluster.
- `variables.tf`: Declares variables used throughout the Terraform configuration.
- `versions.tf`: Specifies the required Terraform version and provider versions.
- `vpc.tf`: Configures the Virtual Private Cloud (VPC) and related networking resources.

## Prerequisites

Before you begin, ensure that you have:

- Terraform installed on your local machine.
- AWS CLI configured with appropriate access.
- An S3 bucket for storing Terraform state files.

## Setup Instructions

### 1. Clone the Repository

```bash
git clone https://github.com/your-username/terraform-eks-setup.git
cd terraform-eks-setup
```

### 2. Initialize Terraform

Run the following command to initialize Terraform, which will download the necessary provider plugins.

```bash
terraform init
```

### 3. Review and Modify Variables

Review the `variables.tf` file to adjust any variables specific to your environment, such as region, VPC CIDR, etc.

### 4. Plan the Deployment

Generate an execution plan to preview the changes Terraform will apply:

```bash
terraform plan
```

### 5. Apply the Configuration

Apply the configuration to create the EKS cluster and related resources:

```bash
terraform apply
```

### 6. Access the EKS Cluster

Once the cluster is created, you can access it using the Kubernetes CLI (`kubectl`). The cluster details can be found in the output values.


## Screenshots and Explanations

### 1. **Terraform Plan Output**

![image](https://github.com/user-attachments/assets/f41aba97-4059-4a94-ba4e-d835a2ae2f70)

 This screenshot demonstrates that Terraform has successfully generated an execution plan, detailing all the resources it will manage.

### 2. **EKS Cluster in AWS Console**

![image](https://github.com/user-attachments/assets/797abb58-0838-48b9-a1d0-a4dd4d28fd5e)

This screenshot confirms that the EKS cluster was successfully created, displaying the cluster name, status, and endpoint.

### 3. **VPC and Subnets in AWS Console**

![image](https://github.com/user-attachments/assets/4da73319-2dc0-4414-8525-99479c030459)

This shows the network infrastructure created by Terraform, including the VPC and subnets where the EKS cluster resides.

## Cleanup

To destroy all resources created by Terraform, run the following command:

```bash
terraform destroy
```
