# ML-KEM (FIPS 203) — Cryptographic Operation Layer Stack

Interactive 3D visualization of the ML-KEM post-quantum key encapsulation mechanism, showing the full mathematical operation stack with FIPS 203 pseudocode. Built to explain how ML-KEM works in Signal's PQXDH triple ratchet and other post-quantum deployments.

**🔗 Live:** [https://secwest.github.io/mlkem-stack/](https://secwest.github.io/mlkem-stack/)

---

## What This Covers

### 🔐 ML-KEM (FIPS 203)

ML-KEM (Module Lattice-Based Key Encapsulation Mechanism) is the NIST-standardized post-quantum key encapsulation scheme derived from CRYSTALS-Kyber. It provides IND-CCA2 security against both classical and quantum adversaries.

This visualization breaks down the full cryptographic operation stack:

- **KeyGen** — polynomial sampling, NTT transforms, matrix-vector multiplication
- **Encapsulation** — shared secret generation with lattice-based encryption
- **Decapsulation** — inverse NTT, decryption, Fujisaki–Okamoto implicit rejection
- **Underlying math** — Ring-LWE, polynomial arithmetic in ℤq[X]/(X^256 + 1), Number Theoretic Transform

### 📡 Applications

- **Signal PQXDH** — Post-quantum Extended Diffie-Hellman used in Signal's triple ratchet protocol
- **TLS 1.3** — Hybrid key exchange (X25519 + ML-KEM-768) deployed by Cloudflare, Google
- **WireGuard** — Post-quantum tunnel proposals
- **HPKE** — Hybrid Public Key Encryption with ML-KEM

## Tech Stack

| Component | Source |
|-----------|--------|
| Three.js r128 | cdnjs.cloudflare.com |

**Zero dependencies to install.** Single self-contained HTML file (~60 KB) with inline CSS/JS. No build step.

## Run Locally

```bash
python3 -m http.server 8000
# Open http://localhost:8000
```

Or open `index.html` directly in a browser.

## License

[MIT](LICENSE)
