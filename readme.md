#### Prerequisites

This is the "app" repo that conains the Kubernetes deployment and services that are intented to be used in conjunction with the already provisioned AWS infrastructue of my other repo. In general the following are the general "prerequisites" to use code (as-is) of the present repository.

 - AWS configured.
 - EKS Cluster configured.
 - Kuberntes installed and access to `kubectl` command.
 - `kubectl` configured in such a way that it has access to the Kuberentes cluster in AWS.

#### Instructions

The `app.yaml`file is represents the containerized application to be deployed to the EKS Cluster.
Other `yaml` files represent Kubernetes services that are required

Any changes made to any `yaml` file need to be applied using the following command:

`kubectl apply -f <path_to_file.yaml>`

Those files need to be applied by the`kubectl apply` command at least once, so the app and the load balancers are created/deployed to the EKS Cluster, and thus making the app accesible over the internet.

Once `app.yaml` and `load-balancer.yaml` are succesfully applied, run `kubectl get svc`.
The  EXTERNAL-IP field of the public-lb service corresponds to the address you can paste on the browser to see the deployed app.

The same address can be found in the "DNS name" column of the same load balancer in the Load Balancers section of the AWS Console.