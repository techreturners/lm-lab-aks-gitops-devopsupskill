# AKS and Terraform

This repository shows examples and guides for using [Terraform](https://terraform.io) to provision a [AKS (Azure Kubernetes Service) Cluster](https://azure.microsoft.com/en-gb/services/kubernetes-service/) on Azure

As well as the instructions below we've also created a suite of [FAQ's](./docs/FAQS.md) that are worth reviewing if you experience any interesting challenges.


## Instructions

### Pre-requisites

Leading on from session 3 this repository provides instruction for both provisioning your cluster, pushing docker images to your own container registry and adopting a GitOps workflow using ArgoCD

### Step 1 - Review the differences

The main difference between this repository and the repository you have previously worked with is that we now also provision a container registry.

Specifically, you'll provision your own [Azure Container Registry (ACR)](https://azure.microsoft.com/en-us/services/container-registry/)

You can see the new terraform code within the [acr.tf](./acr.tf) file. This will provision a [container registry](https://registry.terraform.io/providers/hashicorp/azurerm/latest/docs/resources/container_registry) called "devopsupskillregistry" suffixed with a series of random letters.

The reason for the random characters are that container registry names in Azure have to be globally unique so hopefully using the random characters means we won't experience clashes across learners.

### Step 2 - Provision your cluster

You have probably destroyed your Kubernetes cluster following the previous session. 

Follow through the [Provisioning](./docs/PROVISIONING.md) guide to re-provision your Kubernetes cluster.

### Step 3 - Build and push your docker image

The next step is to build the docker image locally and push it up to your newly created container registry.

Follow through the [Pushing Image Guide](./docs/PUSHINGIMAGE.md) for instructions on how to do this.

### Step 4 - Deploy and navigate to ArgoCD

Now you can move on to getting the backend API Python app deployed via Argo.

Follow through the [Argo setup and configuration steps](./docs/ARGO.md)

### Step 5 - Setting up your DevOps workflow in Argo

Great work! If you've got to here you should now be able to see the Argo Dashboard.

All your infrastructure is setup ready to go! Now you can head over to the GitOps repository to setup your workflow.

[https://github.com/techreturners/lm-lab-gitops-approach](https://github.com/techreturners/lm-lab-gitops-approach)

### FAQs

You can find the FAQs [here](./docs/FAQS.md).
