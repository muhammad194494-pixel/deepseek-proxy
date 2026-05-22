# Changelog

Semua perubahan penting di project ini akan didokumentasikan di file ini.

Format berdasarkan [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
dan project ini mengikuti [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

---

## [1.0.0] - 2026-05-22

### Added
- Reverse proxy DeepSeek API dengan auto-solve Proof of Work (PoW)
- Interface OpenAI-compatible (`/v1/chat/completions`, `/v1/models`)
- Support streaming response via Server-Sent Events (SSE)
- Agentic loop — tool calling otomatis hingga task selesai
- Multi-model support: `deepseek-chat`, `deepseek-reasoner`, `expert`, `gpt-4` alias
- Konfigurasi token via `.env` file (tidak hardcode)
- `.env.example` sebagai template konfigurasi
- `.gitignore` untuk proteksi file sensitif
- Cross-platform: Windows, Linux, macOS
- Demo screenshot (server running + curl test)

### Security
- `server.py` dienkripsi dengan pyobfuscator untuk proteksi IP
- PoW solver via WebAssembly (`sha3.wasm`)

---

## [Unreleased]

### Planned
- Docker support
- Health check endpoint (`/health`)
- Unit tests
- CI/CD workflow
