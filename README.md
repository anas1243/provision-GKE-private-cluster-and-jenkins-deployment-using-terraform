# Deploying Python-redis app on GCP using GKE

This Project aimed to Deploy A containerized python-redis web application on A GKE private cluster

## Steps Applyed

### Infrastructure Provisioning using terraform

1. Configured A custom `VPC` with two `private subnets` subnet1 and subnet2
2. Configured A private `Bastion VM` on the subnet1 and A `Nat Gateway` to make sure that the bastion VM can download staff from the internet
3. Configured A private `GKE cluster` on subnet2
4. Configured A `GCR` to push our application image on it
5. Configured two service accounts for both `Bastion vm` and the `private cluster`
6. Assigned the needed roles for both of them (container.admin and storage.admin)
7. Provisioned the infrastructure using the following command

`terraform apply --var-file terraform/var-files/prod.tfvars`
