<div align="center">

```
  ██████╗ ██╗   ██╗██████╗ ██████╗ ██╗██╗  ██╗ █████╗ 
 ██╔═══██╗██║   ██║██╔══██╗██╔══██╗██║╚██╗██╔╝██╔══██╗
 ██║   ██║██║   ██║██████╔╝██████╔╝██║ ╚███╔╝ ███████║
 ██║▄▄ ██║██║   ██║██╔══██╗██╔══██╗██║ ██╔██╗ ██╔══██║
 ╚██████╔╝╚██████╔╝██████╔╝██║  ██║██║██╔╝ ██╗██║  ██║
  ╚══▀▀═╝  ╚═════╝ ╚═════╝ ╚═╝  ╚═╝╚═╝╚═╝  ╚═╝╚═╝  ╚═╝

   ████████╗ ██████╗  ██████╗ ██╗         ███████╗
   ╚══██╔══╝██╔═══██╗██╔═══██╗██║            ███╔╝
      ██║   ██║   ██║██║   ██║██║           ███╔╝ 
      ██║   ██║   ██║██║   ██║██║          ███╔╝  
      ██║   ╚██████╔╝╚██████╔╝███████╗    ███████╗  
      ╚═╝    ╚═════╝  ╚═════╝ ╚══════╝    ╚══════╝  
```

**Qubrixa Toolz** — Discord Server Nuke Tool

![Python](https://img.shields.io/badge/Python-3.10+-8B00FF?style=for-the-badge&logo=python&logoColor=white)
![HTTP2](https://img.shields.io/badge/HTTP%2F2-Enabled-6A0DAD?style=for-the-badge)
![Async](https://img.shields.io/badge/AsyncIO-800+%20Connections-9B30FF?style=for-the-badge)
![License](https://img.shields.io/badge/License-MIT-5B00D4?style=for-the-badge)

</div>

---

## Overview

**Qubrixa Toolz** is a high-performance Discord server nuke tool built on HTTP/2 with an 800-connection async pool. It supports 10 attack vectors — from instant multi-vector bursts to slow trickle attacks — and shows detailed stats after every operation.

---

## Features

- 🔥 **10 Attack Vectors** — channels, roles, webhooks, threads, messages, wipe, full nuke
- ⚡ **HTTP/2 Multiplexing** — 800 keepalive connections, true parallel dispatch
- 📊 **Live Stats** — sent / success / blocked / speed (req/s) / block% after every run
- 🌊 **Multi-Vector Burst** — fires all action types simultaneously
- 🐢 **Slow Burn** — trickle attack spaced to evade threshold detectors
- 💀 **Full Nuke** — automated 5-phase sequence: wipe → channels → roles → webhooks → spam
- 🎨 **Purple Terminal UI** — raw hacker aesthetic, no bloat
- 🔒 **Obfuscated Source** — payload is zlib+base85 encoded

---

## Attack Vectors

| # | Vector | Description |
|---|---|---|
| 1 | **Channel Flood** | Create N channels simultaneously |
| 2 | **Role Flood** | Create N roles simultaneously |
| 3 | **Webhook Flood** | Create N webhooks across all channels |
| 4 | **Thread Flood** | Create N threads across all channels |
| 5 | **Multi-Vector Burst ★** | Channels + roles + webhooks + threads all at once |
| 6 | **Slow Burn** | Trickle N channels with configurable gap — evades window-based detection |
| 7 | **Wave Attack** | Burst → pause → burst — exploits counter reset windows |
| 8 | **Message Spam** | Custom message flooded across all channels |
| 9 | **Wipe Channels** | Delete all channels simultaneously |
| 10 | **Full Nuke ☠** | 5-phase automated sequence |

---

## Stats Output

```
  ┌─ RESULT ──────────────────────────────────────────
  │  test     Channel Flood
  │  time     0.843s
  │  sent     55
  │  success  55
  │  blocked  0
  │  ratelim  0
  │  speed    65.2 req/s
  │  block%   0.0%
  └──────────────────────────────────────────────────
```

---

## Installation

**Requirements:** Python 3.10+

```bash
git clone https://github.com/samir2328/Nuking-Tool
cd Nuking-Tool
pip install -r requirements.txt
python test.py
```

**Dependencies:**
```
httpx[http2]
```

---

## Usage

```
  token  > <bot-token>
  guild  > <server-id>
```

Enter your bot token and target guild ID on launch. Everything else is interactive.

Each vector prompts for:
- **count** — number of actions to fire (default: `55`)
- **channel name** — name prefix for created channels/roles (default: `Nuked`)
- **message** — custom spam content (default: `@everyone @here Nuked By Qubrixa Toolz`)

---

## Architecture

```
test.py
├── Engine        — HTTP/2 async client pool (800 connections)
│   ├── req()     — stat-tracked attack requests
│   └── fetch()   — internal GETs with retry (bypasses stats)
├── Stats         — per-run counter (sent / success / ratelimit / failed)
├── v_*()         — 10 individual attack vector functions
└── main()        — interactive terminal loop
```

---

## Disclaimer

> For educational and authorized use only. The author is not responsible for any misuse of this tool. Only use on servers and accounts you own.

---

<div align="center">

*Qubrixa Toolz — built for the ones who don't guess.*

</div>
