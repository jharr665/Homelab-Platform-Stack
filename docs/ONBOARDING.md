# Onboarding Guide — Platform Stack

This document helps new contributors or operators get started.

## Prerequisites
- Kubernetes cluster provisioned via Rancher (RKE2 recommended).
- kubectl + Helm installed locally.
- Access to GitHub repo with ArgoCD manifests.

## Steps
1. Clone this repo and set up your `.env` file from `.env.example`.
2. Deploy base services:
   ```bash
   helm upgrade --install cilium cilium/cilium -f kubernetes/cni-cilium/values.yaml
   helm upgrade --install ingress-nginx ingress-nginx/ingress-nginx -f kubernetes/ingress-waf/values.yaml
   helm upgrade --install cert-manager jetstack/cert-manager -f kubernetes/cert-manager/values.yaml
