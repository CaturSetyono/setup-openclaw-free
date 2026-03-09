# Setup OpenClaw Free

Panduan lengkap instalasi OpenClaw dan integrasi model gratis dari OpenRouter untuk meningkatkan produktivitas.

---

## Daftar Isi

1. [Pendahuluan](#pendahuluan)
2. [Instalasi OpenClaw](#instalasi-openclaw)
3. [Setup OpenRouter](#setup-openrouter)
4. [Integrasi Model Gratis](#integrasi-model-gratis)
5. [Konfigurasi Workspace](#konfigurasi-workspace)
6. [Penggunaan Sehari-hari](#penggunaan-sehari-hari)
7. [Tips dan Trik](#tips-dan-trik)
8. [Troubleshooting](#troubleshooting)

---

## Pendahuluan

OpenClaw adalah platform AI assistant yang powerful dan fleksibel. Dengan integrasi model gratis dari OpenRouter, Anda bisa mendapatkan akses ke berbagai model AI tanpa biaya tambahan.

### Keuntungan Menggunakan OpenClaw dengan OpenRouter:

- **Gratis** - Akses ke model AI tanpa biaya
- **Fleksibel** - Banyak pilihan model
- **Produktif** - Tingkatkan efisiensi kerja
- **Customizable** - Sesuaikan dengan kebutuhan

---

## Instalasi OpenClaw

### Prasyarat

- Node.js 16+ atau 18+
- npm atau yarn
- Windows, macOS, atau Linux

### Langkah Instalasi

#### 1. Install Node.js

```bash
# Cek versi Node.js
node --version

# Jika belum terinstall, download dari nodejs.org
# atau gunakan package manager:

# Ubuntu/Debian
sudo apt update
sudo apt install nodejs npm

# macOS (Homebrew)
brew install node

# Windows (Chocolatey)
cinst nodejs
```

#### 2. Install OpenClaw

```bash
# Install OpenClaw secara global
npm install -g openclaw

# Cek versi
openclaw --version
```

#### 3. Setup Workspace

```bash
# Buat folder workspace
mkdir openclaw-workspace
cd openclaw-workspace

# Init OpenClaw
openclaw init
```

#### 4. Konfigurasi Awal

```bash
# Setup konfigurasi dasar
openclaw config set model openrouter/arcee-ai/trinity-large-preview:free
openclaw config set thinking false
openclaw config set verbose false
```

---

## Setup OpenRouter

### Membuat Akun OpenRouter

1. Buka [openrouter.ai](https://openrouter.ai)
2. Signup dengan email
3. Verifikasi email
4. Login ke dashboard

### Dapatkan API Key

1. Buka [Dashboard OpenRouter](https://openrouter.ai/dashboard)
2. Klik "API Keys"
3. Generate new API key
4. Copy API key untuk digunakan

### Setup API Key di OpenClaw

```bash
# Set API key OpenRouter
openclaw config set openrouter_api_key YOUR_API_KEY_HERE

# Test koneksi
openclaw test
```

---

## Integrasi Model Gratis

### Model Gratis yang Tersedia

| Model | Provider | Kegunaan |
|-------|----------|----------|
| `arcee-ai/trinity-large-preview:free` | Arcee AI | General purpose |
| `mistralai/Mistral-7B-Instruct-v0.2:free` | Mistral AI | Text generation |
| `togethercomputer/RedPajama-INCITE-Chat-3B-v2:free` | Together AI | Chat |
| `huggyllama/EasyChatBot-7B:free` | Hugging Face | Chatbot |

### Cara Menggunakan Model Gratis

#### 1. Set Default Model

```bash
# Set default model
openclaw config set model arcee-ai/trinity-large-preview:free
```

#### 2. Gunakan Model Spesifik

```bash
# Gunakan model spesifik untuk session ini
openclaw --model mistralai/Mistral-7B-Instruct-v0.2:free
```

#### 3. List Available Models

```bash
# List semua model gratis
openclaw models list

# Filter model gratis
openclaw models list --free
```

---

## Konfigurasi Workspace

### Struktur Folder

```
openclaw-workspace/
├── AGENTS.md          # Konfigurasi agent
├── SOUL.md            # Identitas assistant
├── USER.md            # Informasi user
├── TOOLS.md           # Tools dan konfigurasi
├── MEMORY.md          # Memory assistant
├── HEARTBEAT.md       # Heartbeat configuration
├── IDENTITY.md        # Identitas assistant
├── workspace/         # Folder kerja utama
├── memory/            # Folder memory
└── scripts/           # Folder scripts
```

### Konfigurasi Penting

#### 1. Model Configuration

```bash
# Set model yang sering digunakan
openclaw config set model openrouter/arcee-ai/trinity-large-preview:free

# Set model untuk tugas spesifik
openclaw config set coding_model openrouter/arcee-ai/trinity-large-preview:free
openclaw config set chat_model openrouter/arcee-ai/trinity-large-preview:free
```

#### 2. Thinking Configuration

```bash
# Enable thinking untuk tugas kompleks
openclaw config set thinking true

# Set timeout untuk thinking
openclaw config set thinking_timeout 30
```

#### 3. Memory Configuration

```bash
# Enable memory untuk konteks jangka panjang
openclaw config set memory_enabled true

# Set memory size
openclaw config set memory_size 1000
```

---

## Penggunaan Sehari-hari

### 1. Basic Usage

```bash
# Mulai session
openclaw

# Mulai dengan model spesifik
openclaw --model mistralai/Mistral-7B-Instruct-v0.2:free

# Mulai dengan thinking enabled
openclaw --thinking
```

### 2. Coding Tasks

```bash
# Bantuan coding
openclaw --task "fix bug in main.py"

# Review code
openclaw --task "review PR #123"

# Generate code
openclaw --task "create REST API endpoint"
```

### 3. Content Creation

```bash
# Bantuan menulis
openclaw --task "write blog post about AI"

# Edit konten
openclaw --task "improve this paragraph"

# Research
openclaw --task "research latest AI trends"
```

### 4. Automation

```bash
# Setup automation
openclaw --task "create GitHub Actions workflow"

# Schedule tasks
openclaw --task "setup cron job for daily backup"
```

---

## Tips dan Trik

### 1. Productivity Hacks

#### Quick Commands

```bash
# Quick help
alias oh='openclaw --help'

# Quick thinking
alias ot='openclaw --thinking'

# Quick coding
alias oc='openclaw --task "code:"'
```

#### Keyboard Shortcuts

- `Ctrl+C` - Cancel current operation
- `Ctrl+D` - Exit session
- `Tab` - Autocomplete commands

### 2. Advanced Features

#### Multi-Model Setup

```bash
# Gunakan model berbeda untuk tugas berbeda
openclaw --model arcee-ai/trinity-large-preview:free --task "general chat"
openclaw --model mistralai/Mistral-7B-Instruct-v0.2:free --task "code generation"
```

#### Context Management

```bash
# Set context untuk session
openclaw --context "project: web-app"

# Clear context
openclaw --clear-context
```

### 3. Integration Tips

#### GitHub Integration

```bash
# Setup GitHub CLI
gh auth login

# Gunakan OpenClaw untuk code review
gh pr view --web
openclaw --task "review this PR"
```

#### API Integration

```bash
# Test API endpoints
openclaw --task "test API /users"

# Generate API documentation
openclaw --task "document this API"
```

---

## Troubleshooting

### Common Issues

#### 1. Installation Issues

```bash
# Clear npm cache
npm cache clean --force

# Reinstall OpenClaw
npm uninstall -g openclaw
npm install -g openclaw
```

#### 2. API Issues

```bash
# Test API connection
openclaw test

# Check API key
openclaw config get openrouter_api_key

# Reset API key
openclaw config set openrouter_api_key NEW_API_KEY
```

#### 3. Performance Issues

```bash
# Check system resources
free -h  # Linux
systeminfo  # Windows

# Optimize model usage
openclaw config set model smaller_model
```

### Debug Mode

```bash
# Enable debug mode
openclaw --debug

# Check logs
openclaw logs
```

### Reset Configuration

```bash
# Backup current config
cp ~/.openclaw/config.json config.backup.json

# Reset to default
openclaw config reset
```

---

## FAQ

### Q: Apakah OpenClaw benar-benar gratis?
**A:** OpenClaw gratis, tapi butuh API key dari OpenRouter (beberapa model gratis, beberapa berbayar).

### Q: Model gratis mana yang paling bagus?
**A:** `arcee-ai/trinity-large-preview:free` untuk general purpose, `mistralai/Mistral-7B-Instruct-v0.2:free` untuk coding.

### Q: Bisa digunakan untuk commercial projects?
**A:** Ya, OpenClaw open source dan bisa digunakan untuk commercial projects.

### Q: Bagaimana cara update OpenClaw?
**A:** `npm update -g openclaw`

---

## Resources

### Documentation
- [OpenClaw Docs](https://docs.openclaw.ai)
- [OpenRouter Docs](https://openrouter.ai/docs)

### Community
- [Discord](https://discord.com/invite/clawd)
- [GitHub Issues](https://github.com/openclaw/openclaw/issues)

### Tutorials
- [YouTube Channel](https://youtube.com/@openclaw)
- [Medium Blog](https://medium.com/@openclaw)

---

## Contributing

Feel free to contribute to this guide! If you find any errors or have suggestions, please open an issue or submit a pull request.

### How to Contribute

1. Fork the repository
2. Create a feature branch
3. Commit your changes
4. Push to the branch
5. Create a Pull Request

---

**Version**: 1.0.0  
**Last Updated**: 2026-03-09  
**Author**: Catur Setyono  

---

*Happy coding with OpenClaw!* 🚀