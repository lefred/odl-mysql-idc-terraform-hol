# Lab 4: Terraform - Deployment

## Overview

⏱️ _5-minutes_ (but more waiting)

In this lab, you will deploy your infrastructure code to Oracle Cloud.
  

## Environment Initialization 

The `terraform init` command is used to initialize a working directory containing Terraform configuration files. 
This is the first command that should be run after writing a new Terraform configuration or cloning an existing one from version control. 

💡 It is safe to run this command multiple times.


```
$ terraform init
```

![](images/terminal/term01.png)

⚠️ verify that you are in the correct directory (the one cloned from GitHub where you created the `terraform.tfvars` file.

## Execution Plan

The `terraform plan` command is used to create an execution plan. Terraform will determine what actions are necessary to achieve the desired 
state specified in the configuration files. In our case, a VCN, gateways, compute instances, firewall rules, ... all should be planned:

```
$ terraform plan
```

![](images/terminal/term02.png)

💡 You can see how many operations are required: new resources, changed resources and resource to destroy.

## Deployment

It's finally time to deploy our code to Oracle Cloud Infrastructure. We use `terraform apply`, this is the command used to apply the changes required to reach 
the desired state of the configuration (see `terraform plan`).

```
$ terraform apply
``` 

![](images/terminal/term03.png)

💡 While the deployment is happening, you can verify in OCI Dashboard, the creation of the compute instances:

![](images/gui/07.png)

![](images/gui/08.png)