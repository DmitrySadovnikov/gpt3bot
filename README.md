# Kubernetes Base Config

This repository contains the base Kubernetes configuration files used for deploying applications. These configurations can be used as a starting point for setting up your Kubernetes clusters and deploying your applications.

## Prerequisites

- Kubernetes cluster
- `kubectl` command-line tool installed and configured
- Access to the repository: `git@github.com:DmitrySadovnikov/kubernetes-base-config.git`

## Installation

1. Clone the repository:

    ```sh
    git clone git@github.com:DmitrySadovnikov/kubernetes-base-config.git
    cd kubernetes-base-config
    ```

## Configuration

The repository contains the following configuration files:

- `ingress_nginx_svc.yaml`: Defines the service configuration for the NGINX ingress controller, including load balancer settings and port mappings.
- `ingress-rules.yaml`: Defines the ingress rules for routing traffic to the backend services based on hostnames and paths.
- `backend-web.yaml`: Defines the deployment configuration for the backend web application, including the container image and environment variables.
- `production_issuer.yaml`: Defines the ClusterIssuer configuration for managing TLS certificates using Let's Encrypt.

## Usage

1. Apply the configurations to your Kubernetes cluster:

    ```sh
    kubectl apply -f ingress_nginx_svc.yaml
    kubectl apply -f ingress-rules.yaml
    kubectl apply -f backend-web.yaml
    kubectl apply -f production_issuer.yaml
    ```

2. Verify that the resources have been created:

    ```sh
    kubectl get services -n ingress-nginx
    kubectl get ingress -n production
    kubectl get deployments -n production
    kubectl get clusterissuers -n cert-manager
    ```

3. Access your application using the ingress URL defined in `ingress-rules.yaml`.

## Contributing

Feel free to submit issues or pull requests if you find any bugs or have suggestions for improvements.

## License

This project is licensed under the MIT License.