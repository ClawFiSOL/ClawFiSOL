# ClawFi Security Model

## Overview

ClawFi is designed with security as a primary concern. 

## Threat Model

### Assets to Protect

1. **Exchange API Keys**: Allow trading on connected exchanges
2. **Wallet Information**: Addresses and activity being monitored
3. **Trading Strategies**: Proprietary detection logic
4. **User Credentials**: Dashboard authentication
5. **Signal History**: May reveal trading patterns

### Threat Actors

1. **External Attackers**: Network-based attacks
2. **Malicious Extensions/Apps**: Running on same system
3. **Supply Chain**: Compromised dependencies
4. **Physical Access**: Device theft or unauthorized access

### Attack Vectors

1. API key theft via memory dump or log exposure
2. Man-in-the-middle on API communications
3. Database compromise
4. Session hijacking
5. Social engineering

## Security Measures

### Secret Management

**Encryption at Rest**
- All API keys and secrets encrypted with AES-256-GCM
- Per-secret key derivation using HKDF
- Master key stored in environment variable (never in code/DB)

```
Master Key (env) → HKDF → Per-Secret Key → AES-256-GCM → Encrypted Data
```

**Key Rotation**
- Support for re-encrypting secrets with new context
- Version field for future encryption upgrades

**Never Logged**
- Secrets are redacted in all log output
- Audit logs contain only sanitized data

