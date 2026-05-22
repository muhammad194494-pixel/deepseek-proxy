<div align="center">

```
██████╗ ███████╗███████╗██████╗ ███████╗███████╗███████╗██╗  ██╗
██╔══██╗██╔════╝██╔════╝██╔══██╗██╔════╝██╔════╝██╔════╝██║ ██╔╝
██║  ██║█████╗  █████╗  ██████╔╝███████╗█████╗  █████╗  █████╔╝ 
██║  ██║██╔══╝  ██╔══╝  ██╔═══╝ ╚════██║██╔══╝  ██╔══╝  ██╔═██╗ 
██████╔╝███████╗███████╗██║     ███████║███████╗███████╗██║  ██╗
╚═════╝ ╚══════╝╚══════╝╚═╝     ╚══════╝╚══════╝╚══════╝╚═╝  ╚═╝
                      PoW Proxy — OpenAI Compatible
```

[![Python](https://img.shields.io/badge/Python-3.8+-3776AB?style=for-the-badge&logo=python&logoColor=white)](https://python.org)
[![FastAPI](https://img.shields.io/badge/FastAPI-0.100+-009688?style=for-the-badge&logo=fastapi&logoColor=white)](https://fastapi.tiangolo.com)
[![License](https://img.shields.io/badge/License-MIT-green?style=for-the-badge)](LICENSE)
[![Platform](https://img.shields.io/badge/Platform-Windows%20%7C%20Linux%20%7C%20macOS-lightgrey?style=for-the-badge)]()

> **🚀 Jalankan DeepSeek AI secara lokal dengan antarmuka OpenAI-compatible.**  
> Satu proxy, semua app yang support OpenAI langsung bisa pakai DeepSeek.

</div>

---

## ✨ Fitur Utama

| Fitur | Keterangan |
|-------|-----------|
| 🔁 **OpenAI Compatible** | Ganti base URL — langsung jalan tanpa ubah kode app |
| ⚡ **Streaming** | Response real-time dengan Server-Sent Events |
| 🤖 **Agentic Loop** | Tool calling otomatis hingga task selesai |
| 🔐 **Token Aman** | Token disimpan di `.env`, tidak hardcode |
| 🌍 **Cross Platform** | Windows, Linux, macOS, VPS |
| 🧠 **Multi Model** | deepseek-chat, deepseek-reasoner, expert, gpt-4 alias |

---

## 📁 Struktur Project

```
📦 deepseek-pow-proxy/
├── 🐍 fixed3_v5.py        ← entry point utama
├── 🔧 sha3.wasm           ← PoW solver (wajib ada)
├── 📋 requirements.txt    ← semua dependency
├── 🔑 .env                ← token kamu (tidak di-push)
├── 📄 .env.example        ← template konfigurasi
├── 🚫 .gitignore          ← proteksi file sensitif
└── 📖 README.md           ← kamu lagi baca ini
```

---

## ⚙️ Instalasi

### 1️⃣ Clone Repository

```bash
git clone https://github.com/username/deepseek-pow-proxy.git
cd deepseek-pow-proxy
```

### 2️⃣ Install Dependencies

```bash
pip install -r requirements.txt
```

### 3️⃣ Setup Token

```bash
# Salin template .env
cp .env.example .env

# Buka .env dan isi token DeepSeek kamu
# DEEPSEEK_TOKEN=token_kamu_disini
```

> 💡 Dapatkan token di: [chat.deepseek.com](https://chat.deepseek.com) → Settings → API

### 4️⃣ Jalankan

```bash
python fixed3_v5.py
```

```
╔══════════════════════════════════════════════╗
║     DeepSeek PoW Proxy — OpenAI Compatible  ║
╠══════════════════════════════════════════════╣
║  Base URL : http://localhost:7000/v1         ║
║  Docs     : http://localhost:7000/docs       ║
╚══════════════════════════════════════════════╝
```

---

## 🔌 Cara Pakai di App Lain

Ganti setting di app kamu dengan:

```
Base URL  :  http://localhost:7000/v1
API Key   :  ds-free  (isi bebas)
Model     :  deepseek-chat
```

### Contoh dengan Python `openai` SDK

```python
from openai import OpenAI

client = OpenAI(
    base_url="http://localhost:7000/v1",
    api_key="ds-free"
)

response = client.chat.completions.create(
    model="deepseek-chat",
    messages=[{"role": "user", "content": "Halo!"}]
)

print(response.choices[0].message.content)
```

### Model yang Tersedia

| Model | Alias |
|-------|-------|
| `deepseek-chat` | `expert` |
| `deepseek-reasoner` | `expert` |
| `gpt-4` / `gpt-4o` | → `expert` |
| `gpt-3.5-turbo` | → `expert` |

---

## 📦 Dependencies

```
fastapi        ← web framework
uvicorn        ← ASGI server
wasmtime       ← PoW solver runtime
requests       ← HTTP client
python-dotenv  ← baca .env
```

---

## 🤝 Kontribusi

Pull request dan issue sangat diterima!

1. Fork repo ini
2. Buat branch baru: `git checkout -b fitur-baru`
3. Commit: `git commit -m "tambah fitur baru"`
4. Push: `git push origin fitur-baru`
5. Buat Pull Request

---

<div align="center">

**Dibuat dengan ❤️ — DeepSeek PoW Proxy**

⭐ Kalau project ini membantu, kasih bintang ya!

</div>
