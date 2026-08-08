# GPG Asymmetric Encryption Lab (Kali Linux)

**Hands-on lab implementing asymmetric encryption, digital signatures, and key management with GnuPG, completed as part of module MF0489_3 — Cryptography and Secure Communications, within the IFCT0109 — Seguridad Informática (SEPE, Level 3) certification.**

---

## Overview

This lab implements a full asymmetric encryption workflow with [GnuPG](https://gnupg.org/) on a Kali Linux virtual machine: key pair generation, public key exchange, file encryption/decryption, digital signing and verification, and keyring management (import, export, revocation). The goal is to apply the theory behind public-key cryptography — confidentiality, integrity, authenticity, and the web of trust — as a hands-on, command-line exercise rather than through a GUI wrapper.

## Environment

| Component | Detail |
|---|---|
| Hypervisor | VMware Workstation |
| Operating system | Kali Linux |
| Main tool | GnuPG (GPG) |

## Objective

Implement a complete asymmetric encryption flow with GPG to guarantee confidentiality, integrity, and authenticity of information in a secure communications scenario, working on a Kali Linux VM.

## Methodology

1. **Key pair generation** (public/private) with `gpg --full-generate-key`.
2. **Public key exchange** to establish a trust channel between two parties.
3. **File encryption/decryption** with `gpg --encrypt` / `gpg --decrypt`.
4. **Digital signing** of files (`gpg --sign`) and **verification** (`gpg --verify`).
5. **Keyring management**: import, export, and revocation of keys.

## Commands used

```bash
# Generate a key pair
gpg --full-generate-key

# List available keys
gpg --list-keys
gpg --list-secret-keys

# Export a public key
gpg --export -a "username" > public_key.asc

# Import another user's public key
gpg --import public_key.asc

# Encrypt a file for a recipient
gpg --encrypt --recipient "recipient_name" file.txt

# Decrypt a received file
gpg --decrypt file.txt.gpg > file_decrypted.txt

# Sign a file
gpg --sign file.txt

# Verify a signature
gpg --verify file.txt.gpg
```

## Concepts applied

- Asymmetric cryptography (public/private key pair)
- Confidentiality, integrity, and authenticity of information (CIA triad applied to communications)
- Web of trust / key trust management
- Secure communications best practices

## What this demonstrates

- Understanding of public-key cryptography fundamentals at the command line, without relying on a GUI wrapper.
- Ability to reason about trust in a two-party exchange: why sharing the *public* key (never the private one) is what makes secure communication possible.
- Familiarity with the full key lifecycle: generation → distribution → use (encrypt/sign) → verification → revocation.

## Evidence gap — honest note

This README documents the procedure and commands executed during the lab, but does not yet include captured terminal output (key fingerprints, an encrypted file sample, a `gpg --verify` result). Rather than fabricate example output, this is left as an open item: the single highest-value addition to this repo is a screenshot or pasted output of `gpg --list-keys` (showing the generated key pair) and of a successful `gpg --verify` run. That is what turns this from "documented procedure" into "proven execution."

## Disclaimer

All commands were executed inside a private, self-owned Kali Linux virtual machine, for training purposes only, as part of the IFCT0109 certification. No third-party systems or real recipients were involved.

---

**Bernat Marcet Claramunt** — IFCT0109, Seguridad Informática (SEPE, Nivel 3)
