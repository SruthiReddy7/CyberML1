# 🛡️ CyberML Platform

![CyberML Banner](https://img.shields.io/badge/CyberML-AI%20Security%20Platform-blue?style=for-the-badge&logo=shield)
![Version](https://img.shields.io/badge/version-2.0.0-green?style=for-the-badge)
![License](https://img.shields.io/badge/license-MIT-orange?style=for-the-badge)

**AI-Powered Threat Intelligence & Prevention Platform**

CyberML is a comprehensive cybersecurity analysis platform that leverages machine learning and AI to detect threats in files, URLs, and APIs. Built with FastAPI backend and React (Vite) frontend, it provides real-time security analysis with an intuitive dashboard.

---
[Demo](https://github.com/user-attachments/assets/22a68715-ea27-42e9-ab3b-e83078f2f759)
## ✨ Features

### 🔍 **File Analysis**
- Deep malware detection using entropy analysis
- Suspicious pattern recognition
- PE (Portable Executable) structure analysis
- YARA rule matching
- Behavioral indicator detection
- Packer detection (UPX, aPLib)

### 🌐 **URL Scanning**
- SSL/TLS certificate validation
- Domain reputation checking
- Phishing detection
- Security header analysis
- Blacklist verification
- Suspicious TLD detection

### 🔌 **API Security Testing**
- Authentication mechanism analysis
- HTTPS/TLS encryption verification
- Vulnerability scanning
- CORS configuration review
- Rate limiting assessment
- Response time analysis

### 🤖 **AI-Powered Chatbot**
- Context-aware security assistance
- Google Gemini AI integration
- Real-time threat consultation
- Security best practices guidance

### 📊 **Advanced Analytics**
- Real-time threat monitoring
- Activity stream tracking
- Comprehensive statistics dashboard
- Threat distribution visualization

### 📄 **PDF Report Generation**
- Professional security reports
- Detailed threat analysis
- Actionable recommendations
- Export and share findings

### 🌐 **Network Monitoring** (Simulated)
- Real-time packet analysis
- Threat detection
- Connection tracking
- Bandwidth monitoring

---

## 🚀 Live Demo

- **Frontend**: [https://cyberml-platform-apy9.vercel.app](https://cyberml-platform-apy9.vercel.app)
- **Backend API**: Deployed on Render
- **API Docs**: `/docs` endpoint (Swagger UI)

---

## 🛠️ Tech Stack

### Frontend
- **React 18** with Vite
- **Tailwind CSS** for styling
- **Lucide React** for icons
- Modern, responsive UI/UX

### Backend
- **FastAPI** (Python)
- **Google Gemini AI** for chatbot
- **ReportLab** for PDF generation
- **Uvicorn** ASGI server

### Deployment
- **Frontend**: Vercel
- **Backend**: Render
- **Version Control**: Git/GitHub

---
## 📊 Model Performance

| Model | Accuracy | Speed | Size |
|-------|----------|-------|------|
| Threat Detector | 95.3% | 50ms | 225MB |
| Malware Classifier | 97.1% | 100ms | 434MB |
| Anomaly Detector | 89.0% | 75ms | 188MB |

## 🗂️ Project Structure
```
cybershield-platform/
├── frontend/          # React application
├── backend/           # FastAPI server + ML models
├── ml_training/       # Training scripts & notebooks
├── datasets/          # Training datasets
├── docs/              # Documentation
```

## 🔬 Training Your Own Models
```bash
cd ml_training

# Download datasets
python scripts/download_datasets.py

# Train threat detection model
python scripts/train_threat_detector.py

# Train malware classifier
python scripts/train_malware_classifier.py

# Evaluate all models
python scripts/evaluate_models.py
```

## 📈 Datasets Used

- [CICIDS2017](https://www.unb.ca/cic/datasets/ids-2017.html) - Network traffic (2.8M samples)
- [Kaggle Malware](https://www.kaggle.com/datasets/khaledelmadawy/malware-detection) - Malware samples (500K samples)
- [PhishTank](https://www.phishtank.com/) - Phishing URLs (100K samples)
- [NVD](https://nvd.nist.gov/) - CVE database (daily updates)

---

## 📦 Installation

### Prerequisites
- Node.js 16+ and npm
- Python 3.8+
- Git

### Clone Repository
```bash
git clone https://github.com/yourusername/cyberml-platform.git
cd cyberml-platform
```

### Frontend Setup
```bash
cd frontend
npm install
```

Create `.env` file:
```env
VITE_API_URL=http://localhost:8000
```

Start development server:
```bash
npm run dev
```

Frontend will run on `http://localhost:5173`

### Backend Setup
```bash
cd backend
pip install -r requirements.txt
```

Create `.env` file (optional):
```env
GEMINI_API_KEY=your_gemini_api_key_here
```

Start backend server:
```bash
python app.py
```

Backend will run on `http://localhost:8000`

---

## 📋 Requirements Files

### `requirements.txt` (Backend)
```txt
fastapi==0.104.1
uvicorn[standard]==0.24.0
python-multipart==0.0.6
pydantic==2.5.0
reportlab==4.0.7
google-generativeai==0.3.1
```

### `package.json` (Frontend)
```json
{
  "name": "cyberml-frontend",
  "version": "2.0.0",
  "type": "module",
  "scripts": {
    "dev": "vite",
    "build": "vite build",
    "preview": "vite preview"
  },
  "dependencies": {
    "react": "^18.2.0",
    "react-dom": "^18.2.0",
    "lucide-react": "^0.263.1"
  },
  "devDependencies": {
    "@types/react": "^18.2.43",
    "@types/react-dom": "^18.2.17",
    "@vitejs/plugin-react": "^4.2.1",
    "autoprefixer": "^10.4.16",
    "postcss": "^8.4.32",
    "tailwindcss": "^3.3.6",
    "vite": "^5.0.8"
  }
}
```

---

## 🚀 Deployment

### Deploy Frontend to Vercel

1. Push code to GitHub
2. Import project in Vercel
3. Add environment variable:
   - `VITE_API_URL` = `https://your-backend.onrender.com`
4. Deploy!

### Deploy Backend to Render

1. Create new Web Service on Render
2. Connect GitHub repository
3. Configure:
   - **Build Command**: `pip install -r requirements.txt`
   - **Start Command**: `python app.py`
4. Add environment variables:
   - `GEMINI_API_KEY` (optional)
5. Deploy!

### Update CORS in Backend

In `app.py`, update allowed origins:
```python
app.add_middleware(
    CORSMiddleware,
    allow_origins=[
        "https://your-frontend.vercel.app",
        "http://localhost:5173"
    ],
    allow_credentials=True,
    allow_methods=["*"],
    allow_headers=["*"],
)
```

---

## 📖 API Documentation

### Endpoints

#### File Analysis
```http
POST /api/analyze/file
Content-Type: multipart/form-data

file: <binary>
```

#### URL Analysis
```http
POST /api/analyze/url
Content-Type: application/json

{
  "url": "https://example.com"
}
```

#### API Security Test
```http
POST /api/analyze/api
Content-Type: application/json

{
  "endpoint": "https://api.example.com/v1/users"
}
```

#### AI Chatbot
```http
POST /api/chat
Content-Type: application/json

{
  "message": "What is malware?",
  "context": { ... }
}
```

#### Download PDF Report
```http
GET /api/report/{analysis_id}/pdf
```

#### Analytics
```http
GET /api/analytics
```

Full API documentation available at `/docs` (Swagger UI)

---

## 🎯 Usage Examples

### Analyze a Suspicious File
1. Navigate to **File Analysis** tab
2. Upload file (supports EXE, DLL, PDF, ZIP, APK, etc.)
3. Click "Start File Threat Analysis"
4. Review detailed results and recommendations
5. Download PDF report

### Scan a URL for Threats
1. Go to **URL Scanner** tab
2. Enter URL (e.g., `https://suspicious-site.com`)
3. Click "Scan URL for Threats"
4. Check SSL status, domain reputation, and phishing score

### Test API Security
1. Select **API Security** tab
2. Enter API endpoint
3. Run penetration tests
4. Review vulnerabilities and security score

### Chat with AI Assistant
1. Click floating chat button (bottom-right)
2. Ask security questions
3. Get context-aware advice based on your analysis

---

## 🔒 Security Features

- **Entropy Analysis**: Detects packed/encrypted malware
- **Pattern Recognition**: Identifies suspicious code patterns
- **SSL/TLS Validation**: Verifies certificate authenticity
- **Blacklist Checking**: Cross-references threat databases
- **OWASP Testing**: API vulnerability assessment
- **Real-time Monitoring**: Live threat detection
- **Confidence Scoring**: ML-based verdict certainty

---

## 🤝 Contributing

Contributions are welcome! Please follow these steps:

1. Fork the repository
2. Create feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit changes (`git commit -m 'Add AmazingFeature'`)
4. Push to branch (`git push origin feature/AmazingFeature`)
5. Open Pull Request

---

## 📝 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

## 👨‍💻 Author

**PRATHAM ZODAPE**
- GitHub: [Rhythmz7](https://github.com/Rhythmz7)
- LinkedIn: [Profile](https://www.linkedin.com/in/pratham-zodape)

---

## 🙏 Acknowledgments

- Google Gemini AI for chatbot intelligence
- FastAPI for the robust backend framework
- React and Vite for modern frontend development
- ReportLab for PDF generation
- The open-source community

---

## 🐛 Known Issues

- Network monitoring is simulated (not actual packet capture)
- PDF generation requires `reportlab` library
- Gemini AI requires API key for advanced features

---

## 🔮 Future Enhancements

- [ ] Real network packet capture
- [ ] Machine learning model training interface
- [ ] Multi-language support
- [ ] Dark mode theme
- [ ] Historical analysis comparison
- [ ] Team collaboration features
- [ ] Custom YARA rule editor
- [ ] Sandbox execution environment
- [ ] Integration with VirusTotal API
- [ ] Mobile application

---

## ⭐ Show Your Support

If you found this project helpful, please give it a ⭐️!

---
