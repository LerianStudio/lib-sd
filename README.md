# 🧩 Golang Library Boilerplate

## Overview

This repository is a boilerplate for creating **private Go libraries** at Lerian.  
It provides a ready-to-use setup for building, versioning, and publishing internal packages using:

- Go Modules
- GitHub Actions with [Semantic Release](https://semantic-release.gitbook.io/)
- Private Go proxy ([Athens](https://athens.lerian.net)) for secure distribution

It's ideal for shared SDKs, internal utilities, and cross-service packages.

---

## Quick Start

1. **Clone the repository:**
    ```bash
    git clone https://github.com/LerianStudio/golang-library-boilerplate.git
    cd golang-library-boilerplate
    ```

2. **Update module path in `go.mod`:**
    ```go
    module github.com/lerianstudio/your-lib-name
    ```

3. **Push to your new repository:**
    ```bash
    git remote set-url origin git@github.com:LerianStudio/your-lib-name.git
    git push -u origin main
    ```

---

## Publishing via Athens Proxy

This project is automatically published to the private Athens proxy (`https://athens.lerian.net`) when a Git tag is pushed.

### How it works:

- Tags like `v1.0.0` trigger the release pipeline
- The pipeline caches the module in the proxy
- Other projects can fetch the module securely and consistently

---

## Local Development

1. **(Optional) Configure your Go proxy locally:**
    ```bash
    export GOPROXY=https://athens.lerian.net,direct
    ```

2. **(Strict) Enforce proxy-only mode (no**
