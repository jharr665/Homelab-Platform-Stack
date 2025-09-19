
---

## `docs/SECURITY.md`
```markdown
# Security Model — Platform Stack

## Layers of Defense
- **Network**: Cilium CNI with mTLS and default-deny NetworkPolicies.
- **Ingress**: NGINX Ingress Controller with ModSecurity OWASP CRS.
- **Authentication**: Authentik SSO with MFA required for all dashboards.
- **Authorization**: Kubernetes RBAC with least privilege roles.
- **Policy Enforcement**: Kyverno (image policies, drop capabilities, probes required).
- **Runtime Detection**: Falco monitoring for suspicious syscalls.

## Supply Chain
- Harbor as private OCI registry.
- All images signed with Cosign.
- Trivy scanning on push + Trivy Operator scanning in cluster.

## Best Practices
- Rotate API tokens every 90 days.
- Avoid `latest` tags in manifests.
- Use PodSecurityStandards: `restricted` baseline for all namespaces.
- Send Falco & Kyverno alerts to SOC stack (Wazuh/Security Onion).
