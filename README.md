# TTAPI Onboarding Tool

> **Version 0.1.185** | Built on 2025-07-22

🚀 **Cross-platform onboarding tool for TTAPI team members**

Secure, automated setup for SSH keys, GPG keys, GitHub authentication, and access request generation.

## 🎯 Quick Start

### 1. Download

Get the latest binary for your platform from [**Releases**](https://github.com/githubrobbi/ttapi-onboarding/releases/latest):

| Platform | Download | Size |
|----------|----------|------|
| **🍎 macOS (Apple Silicon)** | [`ttapi-onboard-macos-arm64`](https://github.com/githubrobbi/ttapi-onboarding/releases/latest/download/ttapi-onboard-macos-arm64) | ~1.2 MB |
| **🍎 macOS (Intel)** | [`ttapi-onboard-macos-intel`](https://github.com/githubrobbi/ttapi-onboarding/releases/latest/download/ttapi-onboard-macos-intel) | ~1.4 MB |
| **🐧 Linux (x64)** | [`ttapi-onboard-linux-x64`](https://github.com/githubrobbi/ttapi-onboarding/releases/latest/download/ttapi-onboard-linux-x64) | ~1.6 MB |
| **🪟 Windows (x64)** | [`ttapi-onboard-windows-x64.exe`](https://github.com/githubrobbi/ttapi-onboarding/releases/latest/download/ttapi-onboard-windows-x64.exe) | ~1.3 MB |

### 2. Make Executable (macOS/Linux)

```bash
chmod +x ttapi-onboard-*
```

### 3. Run Setup

```bash
# Interactive setup (recommended)
./ttapi-onboard-macos-arm64 setup

# Or with parameters
./ttapi-onboard-macos-arm64 setup --name "Your Name" --email "you@example.com" --github-username "yourusername"
```

### 4. Follow Prompts

The tool will guide you through:
- SSH key generation
- GPG key creation
- GitHub authentication
- Access request generation

### 5. Wait for Approval

- The tool generates an access request file
- Send this file to your team lead
- **Wait for approval notification** before proceeding

### 6. After Approval

- Follow the setup instructions in the main TTAPI repository README
- Use the curl command provided in the main repo
- The main repository setup script will guide you through remaining steps

## 🛠️ What This Tool Does

### 🔐 Security Setup
- **SSH Key Generation**: Creates Ed25519 SSH keys for secure GitHub access
- **GPG Key Creation**: Generates GPG keys for commit signing
- **Secure Storage**: Keys stored in standard locations (`~/.ssh/`, `~/.gnupg/`)

### ⚙️ Configuration
- **Git Configuration**: Sets up name, email, and signing preferences
- **GitHub Authentication**: Configures SSH and GPG keys with GitHub
- **Environment Validation**: Verifies all tools and access are working

### 🔍 Access Request & Verification
- **Access Request Generation**: Creates request file for admin approval
- **System Validation**: Checks all requirements are met
- **Setup Verification**: Ensures keys and configuration are correct
- **Access Testing**: Verifies GitHub connectivity (after admin approval)

## 📋 Prerequisites

Before running the onboarding tool, ensure you have:
- ✅ **Git** installed and accessible from command line
- ✅ **Internet connection** for GitHub API access
- ✅ **Terminal/Command Prompt** access
- ✅ **GitHub account** (if you don't have one, create at [github.com](https://github.com))

## 🎮 Available Commands

```bash
# Complete onboarding process (generates access request)
./ttapi-onboard setup

# Generate keys only (no GitHub setup)
./ttapi-onboard generate-keys

# Verify existing setup (after admin approval)
./ttapi-onboard verify-access

# Validate system requirements
./ttapi-onboard validate

# Show system information
./ttapi-onboard system-info

# Get help
./ttapi-onboard --help
```

## 🔍 Security & Verification

### Binary Integrity
All binaries include SHA256 checksums for verification:

```bash
# Download checksums
curl -L https://github.com/githubrobbi/ttapi-onboarding/releases/latest/download/checksums.txt

# Verify your download (macOS/Linux)
sha256sum ttapi-onboard-* && cat checksums.txt

# Verify your download (Windows)
certutil -hashfile ttapi-onboard-windows-x64.exe SHA256
```

### Security Features
- ✅ **No proprietary code** - Safe for public distribution
- ✅ **No embedded secrets** - All authentication is user-generated
- ✅ **Standard key formats** - Compatible with all Git/GitHub tools
- ✅ **Local key storage** - Keys never leave your machine
- ✅ **Open source algorithms** - Ed25519 SSH, RSA/Ed25519 GPG

## 🚨 Troubleshooting

### Common Issues

**"Permission denied" on macOS/Linux**
```bash
chmod +x ttapi-onboard-*
```

**"Git not found"**
- Install Git from [git-scm.com](https://git-scm.com/)
- Ensure `git` is in your PATH

**"GitHub authentication failed"**
- Check your internet connection
- Verify GitHub username is correct
- Ensure you have a GitHub account

**"SSH key already exists"**
- The tool will ask if you want to overwrite existing keys
- Choose 'yes' to replace or 'no' to keep existing keys

### Getting Help
1. **Built-in help**: `./ttapi-onboard --help`
2. **System validation**: `./ttapi-onboard validate`
3. **Verbose output**: `./ttapi-onboard -v setup`
4. **Contact your team lead** for TTAPI-specific issues

## 📊 System Requirements

| Component | Requirement | Notes |
|-----------|-------------|-------|
| **Operating System** | macOS 10.15+, Linux (glibc 2.17+), Windows 10+ | 64-bit only |
| **Git** | 2.0+ | Required for repository operations |
| **Internet** | HTTPS access to github.com | For API calls and key upload |
| **Disk Space** | ~10 MB | For tool and generated keys |
| **Permissions** | User home directory write access | For key storage |

## 🎯 What Happens After Setup

1. **SSH Key**: Generated and added to your GitHub account
2. **GPG Key**: Generated and added to your GitHub account for commit signing
3. **Git Config**: Configured with your name, email, and signing key
4. **Access Request**: Generated for admin approval
5. **Pending Approval**: Wait for team lead to grant repository access
6. **Post-Approval**: Follow main repository README for remaining setup steps

## 📄 License

This tool is licensed under the MPL-2.0 License. See individual releases for complete license information.

## 🏢 About

This onboarding tool is designed specifically for TTAPI team members to streamline the setup process for secure development environment configuration.

**Important**: This tool generates an access request that must be approved by your team lead before you can access TTAPI repositories. After approval, follow the instructions in the main TTAPI repository README.

**Repository Purpose**: This repository contains only release binaries for public distribution. Source code is maintained separately in private repositories.

---

**Need help?** Contact your team lead or check the built-in help: `./ttapi-onboard --help`
