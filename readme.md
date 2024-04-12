#### Prerequisites

This is the "app" repo that conains the Kubernetes deployment and services that are intented to be used in conjunction with the already provisioned AWS infrastructue of my other repo. In general the following are the general "prerequisites" to use code (as-is) of the present repository.

 - AWS configured.
 - EKS Cluster configured.
 - Kuberntes installed and access to `kubectl` command.
 - `kubectl` configured in such a way that it has access to the Kuberentes cluster in AWS.

#### Instructions

The `app.yaml`file is represents the containerized application to be deployed to the EKS Cluster.
Other `yaml` files represent kubernetes services that are required

Any changes made to any `yaml` file need to be applied using the following command:

`kubectl apply -f <path_to_file.yaml>`
