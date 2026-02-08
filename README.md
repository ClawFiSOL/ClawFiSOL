# ClawFi Security Model

## Overview

ClawFi - Crypto Intelligence Platform with Browser Extension, Dashboard & API. Apple Liquid Glass UI design.

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


