# Networking — Platform Stack

## Cilium CNI
- eBPF-based, no iptables dependencies.
- Pod-to-pod encryption (mTLS).
- Hubble observability enabled.

## VLANs
- Management: Rancher, Authentik
- Storage: TrueNAS NFS/iSCSI
- Apps: General workloads
- SOC: Logging, Wazuh, Security Onion
- Red-Team: Isolated lab VLAN

## Ingress
- NGINX Ingress Controller with ModSecurity WAF.
- Cert-manager issues TLS certificates (internal CA or Let’s Encrypt).
- Caddy + Authentik alternative available for ForwardAuth-based SSO.
