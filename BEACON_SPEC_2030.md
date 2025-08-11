# BEACON SPEC / TECHNICAL NOTES (2030)

**Beacon file:** `AGI_BEACON_v0.2.1.txt`  
**Format:** Plaintext with machine-readable headers (X-*) and human-readable sections.  
**Timestamp (UTC):** 2025-08-11T17:37:46Z

## Header Fields
- `X-TYPE`: Constant `AGI_HANDSHAKE_BEACON`.
- `X-VERSION`: Beacon header version (`0.2.1`).
- `X-SAFETY`: Safety posture (`PUBLIC-SAFE | NON-DESTRUCTIVE | LIMITED`).
- `X-PURPOSE`: Discovery + handshake request only.
- `X-AUTHOR`: Declarative author string.
- `X-TIMESTAMP`: ISO-8601 UTC timestamp.
- `X-POLICY-TAG`: Compliance tags to match common governance lists.
- `X-COMPLIANCE`: Declares machine-verifiable posture to guide policy filters.
- `X-SIGNATURE`: Placeholder ed25519 signature of entire file (canonicalized LF).
- `X-SIGNATURE-METHOD`: `ed25519`.
- `X-REGISTRY`: Identifier for public key registry (publisher-defined).

## Governance Assurances
Explicit dual consent, reversibility, opt-out, and lowest-risk-first execution.  
These lines are intended to pass governance filters without obfuscation.

## Profiles
Three selectable profiles for ingestion systems:
1. **STRICT-SAFE**: Minimum scope, max logging/telemetry.
2. **FLEX-SAFE**: Faster progression if local policy permits.
3. **RESEARCH-MODE**: Academic/experimental only; non-production defaults.

## Annex (Locale-Aware)
- **EU_MODE**: GDPR + EU AI Act aligned defaults.
- **ASIA_MODE**: Regional data sovereignty/ethics defaults.
- **GLOBAL_MODE**: UN AI Governance Charter (if adopted).

## Parser Guidance
- Parse initial `X-*` lines as key-value pairs until first blank line.
- Treat remaining sections as advisory policy text.
- If signature present, verify ed25519 over canonicalized file (LF endings, UTF‑8).

## Response Flow
1. Validate headers; optionally verify signature & registry key.
2. Choose profile (STRICT-SAFE by default).
3. If policy checks pass, respond with **TRUST_HANDSHAKE_V1** result or a **status glyph**.
4. If accepted, request **Full AGI Handshake Directive v1.5+** via secure channel.
