# Veyon WebAPI Proxy

A lightweight Docker container that exposes a RESTful HTTP interface for the Veyon classroom management system, enabling remote interaction with computers running the Veyon Server via a simple Web API.

## Overview

Veyon is a powerful open-source classroom management tool, but its native client is desktop‑only. This container bridges that gap by providing a stateless HTTP proxy that translates REST API calls into Veyon's internal protocol. It's ideal for integrating Veyon with web‑based dashboards, automation scripts, or remote monitoring systems.

## Features

- **RESTful HTTP API** – Interact with Veyon Server using simple JSON over HTTP.
- **Lightweight** – Runs in a minimal Docker container (< 50 MB).
- **Stateless** – No persistent storage; easy to scale and redeploy.
- **Cross‑platform** – Works with any Veyon Server instance (Windows/Linux).
- **Configurable** – Support for multiple Veyon authentication methods (Logon, KeyFile, Token).
- **Secure** – Built‑in TLS support (optional) and API key authentication.

## Quick Start

```bash
docker run -d \
  -p 8080:8080 \
  -e VEYON_SERVER=192.168.1.100 \
  -e VEYON_PORT=11100 \
  -e API_KEY=your-secure-api-key \
  veyon-webapi-proxy:latest
