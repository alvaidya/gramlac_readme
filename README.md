# GRAMLAC 🤖

**Generative Retrieval And Multi-step Latent Autoregressive Company Intelligence**

A privacy-first, multi-tenant AI platform for company knowledge management with RAG (Retrieval-Augmented Generation) and CALM-inspired reasoning.

[![All Rights Reserved](https://img.shields.io/badge/License-All%20Rights%20Reserved-red.svg)]()
[![Python 3.12+](https://img.shields.io/badge/python-3.12+-blue.svg)](https://www.python.org/downloads/)
[![FastAPI](https://img.shields.io/badge/FastAPI-0.104+-green.svg)](https://fastapi.tiangolo.com/)
[![React](https://img.shields.io/badge/React-18.0+-blue.svg)](https://reactjs.org/)

---

## 🚧 Current Status

**Beta Testing Phase** - We're currently running a closed beta with select enterprise clients to validate features, gather feedback, and optimize performance. Full public release coming soon after we nail down the user experience and scale our infrastructure.

Stay tuned for the official launch announcement!

---

## 🚀 Features

### Core Capabilities
- ✅ **Multi-Tenant Architecture** - Isolated company data with role-based access
- ✅ **AI-Powered Chat** - Context-aware responses using company documents
- ✅ **Document Management** - Upload & index PDFs, DOCX, TXT files
- ✅ **RAG Pipeline** - Retrieval-Augmented Generation with semantic search
- ✅ **CALM Reasoning** - Multi-step latent autoregressive reasoning

### Security & Compliance
- 🔒 **Encryption at Rest** - AES-256 encryption for database and files
- 🔐 **Password Authentication** - Bcrypt hashing with JWT tokens
- 🛡️ **GDPR Compliance** - Data export, deletion, and privacy endpoints
- 📊 **Performance Monitoring** - Real-time metrics and cost tracking
- ⚡ **Rate Limiting** - Protection against abuse and brute force
- 🚦 **Input Validation** - XSS and injection prevention

### Analytics & Observability
- **Role-Scoped Insight**: Members only see their own history—never anyone else’s. Insight is scoped correctly: clarity for decision-makers, privacy for everyone else.
- **Leadership View**: Role-based analytics layer for leaders: tier usage, response times, confidence scores, cost savings, top queries, activity timelines.
- **Member View**: Individuals see only their own activity and costs.
- **Metrics**: API metrics, cache stats, vector DB stats; optional Sentry for errors.

### Infrastructure
- ☁️ **Cloud-Ready** - Supports Redis Cloud (Upstash) and Qdrant Cloud
- 📈 **Caching Layer** - Redis caching for 10-100x faster queries
- 🔍 **Vector Search** - Qdrant for semantic document similarity
- 📉 **Cost Tracking** - Monitor LLM API usage and expenses

---

## 📋 Tech Stack

### Backend
- **FastAPI** - Modern Python web framework
- **Google Gemini** / **OpenAI** - LLM providers
- **Redis** - Caching layer
- **Qdrant** - Vector database
- **Sentence-Transformers** - Text embeddings (all-MiniLM-L6-v2)

### Frontend
- **React 18** - UI library
- **Vite** - Build tool
- **CSS3** - Styling

### Security
- **bcrypt** - Password hashing
- **PyJWT** - Token authentication
- **cryptography** - File encryption
- **Sentry** - Error tracking (optional)


## Configuration

### Required Environment Variables

```bash
# LLM Provider (choose one)
LLM_PROVIDER=gemini  # or 'openai'
GEMINI_API_KEY=your_key_here
OPENAI_API_KEY=your_key_here

# Security
JWT_SECRET_KEY=your_random_256_bit_secret
ENCRYPTION_KEY=your_encryption_key

# Cloud Services (optional - will use localhost if not set)
REDIS_URL=redis://your-upstash-url
QDRANT_URL=https://your-qdrant-cloud-url
QDRANT_API_KEY=your_qdrant_key
```

### Generate Secrets
```bash
# JWT Secret
python -c "import secrets; print(secrets.token_urlsafe(32))"

# Encryption Key
python -c "from cryptography.fernet import Fernet; print(Fernet.generate_key().decode())"
```

---

## API Endpoints

### Authentication
- `POST /api/auth/signup` - Create account
- `POST /api/auth/login` - User login

### Chat
- `POST /api/chat/message` - Send chat message
- `GET /api/chat/history` - Get chat history

### Documents
- `POST /api/documents/upload` - Upload document
- `GET /api/documents/list` - List documents
- `DELETE /api/documents/{id}` - Delete document

### GDPR
- `GET /api/gdpr/export` - Export user data
- `DELETE /api/gdpr/delete-my-data` - Delete user data
- `GET /api/gdpr/privacy-info` - Privacy information

### Monitoring
- `GET /api/metrics` - Performance metrics
- `GET /api/stats` - System statistics
- `GET /health` - Health check


---

## 🐳 Docker Deployment

### Using Docker Compose
```bash
docker-compose up -d
```

---

## 🌐 Deployment

### Railway (Recommended)
1. Create Railway account
2. Connect GitHub repo
3. Add environment variables
4. Deploy with one click

### Vercel (Frontend Only)
```bash
cd frontend
vercel deploy
```
---
## 🔒 Security Features

### Implemented
- ✅ Password hashing (bcrypt)
- ✅ JWT authentication
- ✅ CORS restrictions
- ✅ Request size limits
- ✅ Input sanitization
- ✅ Encryption at rest
- ✅ GDPR compliance
- ✅ Error tracking (Sentry)
- ✅ Structured logging

### Rate Limits
- Signup: 3 per hour per IP
- Login: 5 per minute per IP
- Chat: 20 per minute per user
- Document Upload: File size limited to 20MB

---

## 📈 Performance

### Caching
- Reports: 24-hour TTL
- Web scrapes: 1-hour TTL
- LLM responses: 1-hour TTL

### Cost Tracking
- Gemini Flash: **100% FREE** (15 req/min, 1M tokens/month)
- No API costs when using the free Gemini tier
- Optional: Switch to paid providers (OpenAI) if needed
---

## 📝 License & Copyright

Copyright (c) 2025 Anushka Vaidya. All Rights Reserved.

This project and its source code are proprietary and confidential. Unauthorized copying, modification, distribution, or use of this software, via any medium, is strictly prohibited without explicit written permission from the copyright holder.

**Citation:**
If you reference or discuss this project, please cite as:
```
Vaidya, A. (2025). GRAMLAC: Generative Retrieval And Multi-step Latent
Autoregressive Company Intelligence. GitHub repository.
```

---

## 🙏 Acknowledgments

- Inspired by CALM (Confident Adaptive Language Modeling)
- Built with FastAPI and React
- Powered by Google Gemini / OpenAI
- Hosted on Railway / Vercel

---

## 📧 Support

For questions, feedback, or support inquiries:
- Email: alvaidya00@gmail.com
- Issues: [GitHub Issues](https://github.com/yourusername/GRAMLAC/issues)

---

**Made with ❤️ by the GRAMLAC Team**
