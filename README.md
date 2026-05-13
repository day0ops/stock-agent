# stock-agent

[![Release](https://github.com/day0ops/stock-agent/actions/workflows/release.yml/badge.svg)](https://github.com/day0ops/stock-agent/actions/workflows/release.yml)
[![License](https://img.shields.io/badge/License-Apache%202.0-blue.svg)](LICENSE)
[![Image](https://img.shields.io/badge/registry-GAR-4285F4?logo=googlecloud)](https://console.cloud.google.com/artifacts/docker/field-engineering-apac/australia-southeast1/kasunt)

FastAPI agent wrapping a stock ADK agent, routing tool calls through [agentgateway](https://agentgateway.dev).

## What it does

Accepts natural language queries about stocks, processes them with an ADK-based agent, and forwards MCP tool calls to the stock-server-mcp via agentgateway.

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
