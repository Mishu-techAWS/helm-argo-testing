# Nginx Helm Chart for Argo CD

This is a simple Nginx deployment managed by Helm and Argo CD.

## Repository Structure
```
├── Chart.yaml              # Helm chart metadata
├── values.yaml             # Configurable values
├── templates/
│   ├── deployment.yaml     # Nginx deployment
│   └── service.yaml        # Nginx service
└── argocd/
    ├── nginx-application.yaml  # Argo CD application
    └── project.yaml            # Argo CD project
```

## Configuration

Edit `values.yaml` to modify:
- Replica count
- Image version  
- Resource limits
- Service configuration

## Deployment

1. **Setup Argo CD Application:**
   ```bash
   # Update YOUR_USERNAME in argocd/nginx-application.yaml
   kubectl apply -f argocd/project.yaml
   kubectl apply -f argocd/nginx-application.yaml
   ```

2. **Test GitOps:**
   - Modify `values.yaml` (e.g., change replicaCount)
   - Push to GitHub
   - Watch Argo CD sync automatically

## Usage

This chart is automatically deployed by Argo CD when changes are pushed to this repository.
