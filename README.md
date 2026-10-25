# 🦉 OBGP

<p align="center">
  <img src="https://img.shields.io/badge/Platform-Linux-0a0c10?style=flat-square"/>
  <img src="https://img.shields.io/badge/Category-Security-blue?style=flat-square"/>
  <img src="https://img.shields.io/badge/License-MIT-green?style=flat-square"/>
  <img src="https://img.shields.io/badge/Part%20of-OwlSec%20Toolkit-7b5ea7?style=flat-square"/>
  <img src="https://img.shields.io/badge/Version-1.0-cyan?style=flat-square"/>
</p>

> **OBGP** — part of the OwlSec Toolkit.

---

> ⚠️ **AUTHORISED USE ONLY** — Use only on systems you own or have explicit written permission to test. Unauthorised use is illegal.

---

## 📌 Overview

OBGP audits BGP routing tables exported from your own routers or from looking glasses. It validates route origins against ROA data with RPKI and runs an anomaly engine that scores every prefix for hijack risk. It only analyzes exported tables and never peers with a BGP speaker.

---

## ✨ Features

- Reads simple prefix/AS-path lines and Cisco "show ip bgp" style dumps
- RPKI origin validation against a ROA file (prefix, maxLength, ASN) → valid / invalid / unknown, for IPv4 and IPv6
- Anomaly engine: bogons, MOAS, AS-path loops, private ASNs, heavy prepending, too-short or too-long prefixes, blackhole and graceful-shutdown communities
- Per-prefix hijack score with AS-path and prefix statistics
- Reference for well-known ASNs and BGP communities
- Reports in TXT / JSON / Markdown / CSV / SARIF; exits with code 3 on CRITICAL/HIGH findings

---

## ⚙️ Requirements

- **Linux**
- **No Python installation needed** — runs as a standalone executable

---

## 🚀 Usage

```bash
./OBGP                                       # interactive menu
./OBGP --file table.txt --analyze
./OBGP --file table.txt --rpki --roa roas.csv
./OBGP --file table.txt --hijack
```

Run `./OBGP --help` for the full list of options.

---

## 📦 Part of OwlSec Toolkit

This tool is part of the **OwlSec** suite — a collection of 300+ security and privacy tools.

🔗 [owlsec.org](https://owlsec.org)

---

## ©️ License

MIT License — © Khaled S. Haddad

*Tools are distributed as pre-built executables. Source code is proprietary.*
