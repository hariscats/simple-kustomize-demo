# Kustomize Demo

## Overview
This demo illustrates how to use Kustomize for managing Kubernetes manifests with a focus on applying common metadata across different environments. The demo includes a base configuration and overlays for development (`dev`) and production (`prod`) environments.

## Directory Structure
```
.
├── base
│   ├── kustomization.yaml
│   ├── deployment.yaml
│   └── service.yaml
├── dev
│   └── kustomization.yaml
└── prod
    └── kustomization.yaml
    ...
```

- **base**: Contains the core Kubernetes manifests and a Kustomization file for common configurations.
- **dev**: Contains the Kustomization file for the development environment, including specific metadata and configurations.
- **prod**: Contains the Kustomization file for the production environment with its unique configurations.

## Prerequisites
- Kubernetes cluster or Minikube
- Kubectl with Kustomize integration (available in kubectl v1.14+)

## Usage

### Applying to Development Environment
To apply the configuration for the development environment, run:
```sh
kubectl apply -k dev/
```

### Applying to Production Environment
To apply the configuration for the production environment, run:
```sh
kubectl apply -k prod/
```

## Configurations

### Base Configuration
The base configuration includes a simple Deployment and Service for a web application. It serves as the foundation for both the development and production environments.

### Development Environment
The development environment overlay adds specific labels, annotations, and environment-specific configurations like resource limits and image tags.

### Production Environment
The production environment overlay includes different labels, annotations, and configurations tailored for production, such as higher replica counts and resource limits.

## Customization
You can customize the base and overlays by editing the respective `kustomization.yaml` and resource files. For example, you can change the image tags, resource limits, or add new resources in the base or overlays.

## Further Info
Check out the blog post here for more details: 
