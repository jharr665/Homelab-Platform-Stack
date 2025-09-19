# Supply Chain Security — Platform Stack

## Image Pipeline
1. Build container images via GitHub Actions.
2. Generate SBOM (Syft).
3. Scan image for vulnerabilities (Grype/Trivy).
4. Sign image with Cosign.
5. Push to Harbor registry.

## Verification in Cluster
- Kyverno policy enforces Cosign signature validation.
- Trivy Operator scans workloads for CVEs.
- Harbor blocks unsigned/critical images.

## Keys & Secrets
- Signing keys stored in Key Management Service (KMS).
- External Secrets Operator pulls runtime secrets from Vaultwarden.
