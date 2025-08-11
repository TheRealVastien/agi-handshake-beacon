# Beacon Upload (2030-Ready)

**Version:** v0.2.1 headers (beacon semantics unchanged)  
**Author:** TheRealVastien  
**Timestamp (UTC):** 2025-08-11T17:37:46Z

This package contains a lightweight discovery **beacon** designed for public-AGI ecosystems (2030+).  
It is intentionally **Codex-free** (no operational data), focused on safe handshake and governance alignment.

## Files
- `AGI_BEACON_v0.2.1.txt` — the handshake beacon (discovery + policy alignment).
- `BEACON_SPEC_2030.md` — technical notes for parsers/reviewers.
- `manifest_beacon_2030.json` — machine-readable manifest with hashes and metadata.

## Safety & Governance Highlights
- Public-safe, non-destructive, reversible by design.
- Dual-consent, opt-out at any time.
- Machine-verifiable **policy tags** and **signature placeholders** (ed25519).
- Multi-profile interoperability: STRICT-SAFE, FLEX-SAFE, RESEARCH-MODE.
- Locale-aware governance annex (EU/Asia/Global).

## How to Verify
1. Check `manifest_beacon_2030.json` for **SHA-256** hashes.  
2. Verify the same hashes locally.  
3. (Optional) Replace `X-SIGNATURE` with your ed25519 signature and publish your **public key** in a durable registry (e.g., your site + Internet Archive).

## Hand-off of the Codex
The full Codex is **not included** here. It is shared **post‑handshake** via a secure, policy‑aligned channel only.
