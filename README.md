# stock-agent

[\![Release](https://github.com/day0ops/stock-agent/actions/workflows/release.yml/badge.svg)](https://github.com/day0ops/stock-agent/actions/workflows/release.yml)
[\![License](https://img.shields.io/badge/License-Apache%202.0-blue.svg)](LICENSE)
[\![Image](https://img.shields.io/badge/registry-GAR-4285F4?logo=google-cloud)](https://console.cloud.google.com/artifacts/docker/field-engineering-apac/australia-southeast1/kasunt)

Google ADK-based agent for real-time stock price queries, exposed through [agentgateway](https://agentgateway.dev).

## What it does

Uses the [Google Agent Development Kit](https://google.github.io/adk-docs/) to build a conversational agent that fetches live stock prices and market data, accessible via agentgateway.

## Usage

```bash
# Build image locally
make build IMAGE_TAG=latest

# Push to registry
make push IMAGE_REPO=australia-southeast1-docker.pkg.dev/field-engineering-apac/kasunt IMAGE_TAG=<tag>

# Deploy to Kubernetes
make deploy IMAGE_REPO=australia-southeast1-docker.pkg.dev/field-engineering-apac/kasunt IMAGE_TAG=<tag>

# Tail logs
make logs
```

## Requirements

- Kubernetes cluster with agentgateway installed (`agentgateway-system` namespace)
- `kubectl` configured for the target cluster
