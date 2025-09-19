# GitOps with ArgoCD — Platform Stack

## Principles
- Desired state defined in Git (this repo).
- ArgoCD reconciles cluster to match Git continuously.
- No `kubectl apply` outside CI/CD.

## Workflow
1. Developer pushes change to GitHub.
2. GitHub Actions builds image, pushes to Harbor, signs with Cosign.
3. Helm values/manifest updated in Git.
4. ArgoCD syncs change into cluster.
5. Kyverno/OPA policies block non-compliant workloads.

## Benefits
- Full audit log of changes.
- Easy rollback (revert commit).
- Compliance-friendly (everything as code).
