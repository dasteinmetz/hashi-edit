# Getting Started with Terraform

Terraform allows infrastructure to be expressed as code. In this guide, you will learn how to use Terraform to create infrastructure based on a code snippet. You will install Terraform on a Linux system, use a configuration file to create a Docker provider and provision a server, and then destroy the infrastructure. 

## Prerequisites

To follow this guide you will need:

* A Linux system supported by Terraform. See the list on the [download page on Terraform.io](https://www.terraform.io/downloads.html).
* Docker [installed](https://docs.docker.com/engine/install/) on your local machine.

## Install Terraform

To install Terraform, visit the [Terraform download page](https://www.terraform.io/downloads.html) and download the binary package for your system.

Unzip the package and move the binary to a directory in your system's `PATH`.

Verify the installation by opening a new terminal session and typing `terraform -help`. Terraform is working properly if you see a list of subcommands. Troubleshoot if needed.

With Terraform installed and working, you can create some infrastructure.

## Create a configuration

Terraform creates infrastructure based on configuration files. 

First, create a new directory on your local machine for the configuration file. Name the directory `terraform-demo`.

```shell
$ mkdir terraform-demo
```
Change into the directory. 

```shell
$ cd terraform-demo
```

Next, create a file, `main.tf`, for your Terraform configuration code.

```shell
$ touch main.tf
```

Paste the following lines into the file.

```hcl
provider "docker" {
    host = "unix:///var/run/docker.sock"
}

resource "docker_container" "nginx" {
  image = docker_image.nginx.latest
  name = "training"
  ports {
    internal = 80
    external = 80
  }
}

resource "docker_image" "nginx" {
  name = "nginx:latest"
}
```

## Create the infrastructure

Next, you will create the infrastructure described in the configuration file by running commands to initialize and provision the resources. 

Initialize the Terraform configuration with the `terraform init` command. The Docker provider will be installed. 

```shell
$ terraform init
```

Check for any errors. If it ran successfully, provision the resource with the `terraform apply` command.

```shell
$ terraform apply
```

You will be asked to confirm. Type `yes` and press ENTER. The command might take a few minutes to run. A message indicates that the resource was created.

## Destroy the infrastructure

Finally, destroy the infrastructure by using the `terraform destroy` command. This will remove all resources from the configuration.

```shell
$ terraform destroy
```

Look for a message at the bottom of the output asking for confirmation. Type `yes` and press ENTER. Terraform will destroy the resources it created earlier.

## Next steps

You have installed Terraform, created a configuration file, provisioned a resource, and destroyed the resource. Using Terraform, you created infrastructure with only a few commands and a code snippet.  

Continue exploring: 

* In addition to Docker, see the [list of providers available to use with Terraform](https://www.terraform.io/docs/providers/index.html).

* Learn more about [how to provision infrastructure with Terraform](https://learn.hashicorp.com/terraform).

* Review the [features and benefits of Terraform](https://www.hashicorp.com/products/terraform).
