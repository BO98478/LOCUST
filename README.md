Chicago Linode Workshop
======================

## About

Package of template files, examples, and illustrations for the Chicago Linode Workshop.

## Contents

### Template Files
- Sample Terraform files for deploying an LKE cluster on Linode.
- Sample kubernetes deployment files for starting an application on an LKE cluster.


### Examples

Below are some key commands that will be used in the workshop

- installing git from a shell:

```
sudo apt-get git
```

- Cloning this repository once git is installed:

```
git init && git pull https://github.com/ccie7599/chicago-workshop
```

#### Terraform commands:
- Installing terraform:
```
sudo apt-get update && sudo apt-get install -y gnupg software-properties-common
wget -O- https://apt.releases.hashicorp.com/gpg | \
    gpg --dearmor | \
    sudo tee /usr/share/keyrings/hashicorp-archive-keyring.gpg
echo "deb [signed-by=/usr/share/keyrings/hashicorp-archive-keyring.gpg] \
    https://apt.releases.hashicorp.com $(lsb_release -cs) main" | \
    sudo tee /etc/apt/sources.list.d/hashicorp.list
sudo apt update
sudo apt-get install terraform
```
- Initializing Terraform and planning a deployment:
```
terraform init
terraform plan \
 -var-file="terraform.tfvars"
 ```
 - Applying a terraform plan:
 ```
 terraform apply \
 -var-file="terraform.tfvars"
 ```

#### Kubectl commands:
- installing kubectl:
```
sudo apt-get update
sudo apt-get install -y ca-certificates curl
sudo curl -fsSLo /usr/share/keyrings/kubernetes-archive-keyring.gpg https://packages.cloud.google.com/apt/doc/apt-key.gpg
echo "deb [signed-by=/usr/share/keyrings/kubernetes-archive-keyring.gpg] https://apt.kubernetes.io/ kubernetes-xenial main" | sudo tee /etc/apt/sources.list.d/kubernetes.list
sudo apt-get update
sudo apt-get install -y kubectl
```

- Exposing a kubernetes deployment:
```
kubectl expose deployment nginx-workshop --type=LoadBalancer --name=nginx-workshop --namespace chicago-workshop
```

### Illustrations

The below diagrams illustrate each step of the workshop from an architectural standpoint-




