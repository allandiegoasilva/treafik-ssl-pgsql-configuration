# Traefik Domain Configuration

## Overview

This document provides instructions on how to configure Traefik and generate a certificate.

## Prerequisites

- Ensure you have Docker and Docker Compose installed on your machine.
- Make sure you have created the necessary directory structure for Traefik and your services.

## Traefik Configuration Steps

### 1. Set Permissions for `acme.json`

Before starting Traefik, you need to set the correct permissions for the `acme.json` file, which stores your Let's Encrypt certificates. Run the following command:

```
chmod 600 treafik/acme.json
```

### 2. Start the Traefik Container

Navigate to the Traefik directory and start the Traefik container using Docker Compose:

```
cd treafik
docker compose up -d
```

### 3. Start Your Service with Traefik

After starting Traefik, navigate to your service directory that will use Traefik as a router and start it:

```
cd /provider
docker compose up -d
```

### 4. Certificate Generation

Upon successful startup, Traefik will automatically generate SSL certificates using Let's Encrypt for your configured domains.

#### Notes

Ensure that your Traefik configuration file correctly specifies your routers and entry points.
Verify that your DNS records are correctly set up to point to your Traefik server.
