# 🌱 CropAI - AI-Powered Crop Disease Diagnosis

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Python 3.8+](https://img.shields.io/badge/python-3.8+-blue.svg)](https://www.python.org/downloads/)
[![FastAPI](https://img.shields.io/badge/FastAPI-0.104.1-009688.svg)](https://fastapi.tiangolo.com)
[![TensorFlow](https://img.shields.io/badge/TensorFlow-2.13.0-FF6F00.svg)](https://tensorflow.org)
[![React Native](https://img.shields.io/badge/React%20Native-0.72-61DAFB.svg)](https://reactnative.dev)
[![Build Status](https://img.shields.io/badge/build-passing-brightgreen.svg)](https://github.com/Gatmach/cropai/actions)

> Empowering Kenyan smallholder farmers with intelligent plant health diagnostics through computer vision and mobile technology

## 🚀 Overview

CropAI is an AI-powered crop disease diagnosis system specifically designed for Kenyan smallholder farmers. Our solution combines advanced computer vision, machine learning, and mobile technology to provide instant, accurate disease detection for maize, tomatoes, and beans - helping farmers make informed decisions and improve crop yields.

### 🎯 Problem We're Solving

- **Food Security**: Supporting Kenya's Vision 2030 and UN SDG 2 (Zero Hunger)
- **Agricultural Productivity**: Helping farmers detect diseases early to prevent crop loss
- **Technology Access**: Providing offline-capable solutions for rural areas
- **Knowledge Gap**: Bridging the gap between agricultural expertise and smallholder farmers

## ✨ Features

### 🔬 Core Capabilities
- **Real-time Disease Detection**: Instant diagnosis using smartphone cameras
- **Offline Functionality**: TensorFlow Lite models work without internet
- **Multi-crop Support**: Maize, tomatoes, and beans disease detection
- **High Accuracy**: 92%+ accuracy on disease classification
- **Treatment Recommendations**: Actionable advice for disease management

### 🌍 Localization
- **Multi-language Support**: English and Swahili interfaces
- **Local Context**: Tailored for Kenyan agricultural conditions
- **Cultural Sensitivity**: Designed with local farming practices in mind

### 📱 Technology Stack
- **Frontend**: React Native mobile app
- **Backend**: FastAPI with Python
- **AI/ML**: TensorFlow, Keras, OpenCV
- **Database**: SQLite with SQLAlchemy ORM
- **Deployment**: Docker containerization

## 📸 Screenshots

### Mobile App Interface
*(Screenshots to be added during development)*

### Web Dashboard
*(Dashboard screenshots to be added)*

## 🛠️ Installation

### Prerequisites
- Python 3.8 or higher
- Node.js 16 or higher
- npm or yarn
- Android Studio (for mobile development)
- Git

### Backend Setup

1. **Clone the repository**
   ```bash
   git clone https://github.com/Gatmach/cropai.git
   cd cropai
   ```

2. **Create virtual environment**
   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows: venv\Scripts\activate
   ```

3. **Install dependencies**
   ```bash
   pip install -r requirements.txt
   ```

4. **Set up environment variables**
   ```bash
   cp .env.example .env
   # Edit .env with your configuration
   ```

5. **Initialize database**
   ```bash
   python -c "from src.database import init_db; init_db()"
   ```

6. **Run the backend server**
   ```bash
   uvicorn src.main:app --reload --host 0.0.0.0 --port 8000
   ```

### Frontend Setup

1. **Navigate to frontend directory**
   ```bash
   cd frontend
   ```

2. **Install dependencies**
   ```bash
   npm install
   # or
   yarn install
   ```

3. **Start development server**
   ```bash
   npm start
   # or
   yarn start
   ```

### Mobile App Setup

1. **Navigate to mobile directory**
   ```bash
   cd mobile
   ```

2. **Install dependencies**
   ```bash
   npm install
   # or
   yarn install
   ```

3. **Start Metro bundler**
   ```bash
   npx react-native start
   ```

4. **Run on Android**
   ```bash
   npx react-native run-android
   ```

## 🚀 Usage

### API Endpoints

#### Disease Prediction
```bash
POST /predict
Content-Type: multipart/form-data

curl -X POST "http://localhost:8000/predict" \
  -F "file=@path/to/crop/image.jpg" \
  -F "crop_type=maize"
```

#### Training New Models
```bash
POST /train
Content-Type: application/json

{
  "crop_type": "maize",
  "model_architecture": "mobilenetv2",
  "epochs": 50,
  "batch_size": 32,
  "learning_rate": 0.001
}
```

#### Get Statistics
```bash
GET /statistics
```

### Mobile App Usage

1. **Open the CropAI mobile app**
2. **Select your crop type** (maize, tomato, or beans)
3. **Take a photo** of the affected plant
4. **Get instant diagnosis** with confidence score
5. **View treatment recommendations**
6. **Save results** for future reference

## 🔧 Configuration

### Environment Variables

Create a `.env` file in the root directory:

```env
# Database
DATABASE_URL=sqlite:///./crop_disease.db

# Model Configuration
MODEL_DIR=models
DATASET_DIR=datasets
UPLOAD_DIR=uploads

# API Configuration
API_HOST=0.0.0.0
API_PORT=8000
MAX_FILE_SIZE=10485760  # 10MB

# Security
SECRET_KEY=your-secret-key-here
ALGORITHM=HS256
ACCESS_TOKEN_EXPIRE_MINUTES=30
```

## 🧪 Testing

### Backend Tests
```bash
# Run all tests
pytest

# Run with coverage
pytest --cov=src --cov-report=html

# Run specific test file
pytest tests/test_api.py -v
```

### Frontend Tests
```bash
cd frontend
npm test
```

### Mobile App Tests
```bash
cd mobile
npm test
```

## 📊 Supported Crops & Diseases

| Crop | Diseases Detected |
|------|------------------|
| **Maize** | Healthy, Northern Leaf Blight, Common Rust, Maize Streak Virus |
| **Tomato** | Healthy, Early Blight, Bacterial Wilt, Mosaic Virus, Powdery Mildew |
| **Beans** | Healthy, Bean Common Mosaic, Angular Leaf Spot, Bean Rust |

## 🤝 Contributing

We welcome contributions! Please see our [Contributing Guidelines](CONTRIBUTING.md) for details.

### Development Workflow

1. **Fork the repository**
2. **Create a feature branch**
   ```bash
   git checkout -b feature/amazing-feature
   ```
3. **Make your changes**
4. **Add tests** for new functionality
5. **Run tests** to ensure everything works
6. **Commit your changes**
   ```bash
   git commit -m "feat: add amazing feature"
   ```
7. **Push to your fork**
   ```bash
   git push origin feature/amazing-feature
   ```
8. **Create a Pull Request**

### Commit Convention

We follow [Conventional Commits](https://www.conventionalcommits.org/):

- `feat:` New features
- `fix:` Bug fixes
- `docs:` Documentation changes
- `style:` Code style changes
- `refactor:` Code refactoring
- `test:` Test additions or changes
- `chore:` Maintenance tasks

## 📈 Model Performance

### Current Metrics

| Crop | Accuracy | Precision | Recall | F1-Score |
|------|----------|-----------|--------|----------|
| Maize | 92.3% | 91.8% | 92.1% | 91.9% |
| Tomato | 89.7% | 89.2% | 89.5% | 89.3% |
| Beans | 91.1% | 90.8% | 91.0% | 90.9% |

### Training Data
- **Total Images**: 15,000+
- **Sources**: PlantVillage + Local Kenyan datasets
- **Augmentation**: Advanced image augmentation techniques
- **Validation**: 5-fold cross-validation

## 🏗️ Architecture

### System Overview
```
┌─────────────────┐    ┌─────────────────┐    ┌─────────────────┐
│   Mobile App    │    │   Web Frontend  │    │   Web Dashboard │
│  (React Native) │    │     (React)     │    │     (React)     │
├─────────────────┤    ├─────────────────┤    ├─────────────────┤
│                 │    │                 │    │                 │
│  TensorFlow     │    │  Image Upload   │    │  Analytics      │
│  Lite Models    │    │  & Display      │    │  & Monitoring   │
└─────────┬───────┘    └─────────┬───────┘    └─────────┬───────┘
          │                      │                      │
          └──────────────────────┼──────────────────────┘
                                 │
                    ┌─────────────▼─────────────┐
                    │      FastAPI Backend     │
                    │                          │
                    │  ┌─────────────────────┐ │
                    │  │   ML Pipeline       │ │
                    │  │                     │ │
                    │  │  • Image Processing │ │
                    │  │  • Model Inference  │ │
                    │  │  • Result Caching   │ │
                    │  └─────────────────────┘ │
                    │                          │
                    │  ┌─────────────────────┐ │
                    │  │   Data Layer        │ │
                    │  │                     │ │
                    │  │  • SQLite Database  │ │
                    │  │  • File Storage     │ │
                    │  │  • Model Storage    │ │
                    │  └─────────────────────┘ │
                    └──────────────────────────┘
```

## 🔒 Security

- **Input Validation**: All file uploads are validated
- **Rate Limiting**: API endpoints are rate-limited
- **Data Privacy**: User data is handled according to privacy guidelines
- **Secure Storage**: Sensitive data is encrypted

## 📚 API Documentation

Once the server is running, visit:
- **Interactive API Docs**: http://localhost:8000/docs
- **ReDoc Documentation**: http://localhost:8000/redoc

## 🌍 Deployment

### Docker Deployment

1. **Build the Docker image**
   ```bash
   docker build -t cropai .
   ```

2. **Run the container**
   ```bash
   docker run -p 8000:8000 cropai
   ```

### Production Deployment

For production deployment, see our [Deployment Guide](docs/deployment.md).

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 👥 Team

| Name | Role | Contact |
|------|------|---------|
| **Gatmach Yuol Nyuon** | Lead Developer & AI Specialist | [LinkedIn](https://www.linkedin.com/in/gatmachyuolnyuon) \| [GitHub](https://github.com/Gatmach) |
| **Collins Omollo** | Frontend Developer | [LinkedIn](https://www.linkedin.com/in/collins-omollo-51296629a) \| [GitHub](https://github.com/loskiii) |
| **Meshack Otieno** | Backend Engineer | [LinkedIn](https://www.linkedin.com/in/meshack-otieno-447545363) \| [GitHub](https://github.com/Meshackoo) |
| **Aketch Atem Dau** | Agricultural Consultant | [LinkedIn](https://linkedin.com/in/aketch-atem-2a363b2ba) \| [GitHub](https://github.com/akechsmith) |
| **Methusella Nyongesa** | Backend Developer | [LinkedIn](https://www.linkedin.com/in/methusella-nyongesa-b94a63259) \| [GitHub](https://github.com/OfficialMNM) |

## 🙏 Acknowledgments

- **JKUAT** - Jomo Kenyatta University of Agriculture and Technology
- **JHUB Africa** - Technical mentorship and guidance
- **Dr. Lawrence Nderu** - Project supervision
- **PlantVillage** - Initial dataset source
- **Kenyan Farmers** - Field testing and feedback

## 📞 Contact & Support

- **Email**: gatmachyuol@gmail.com
- **Project Website**: [CropAI Landing Page](https://cropai.jkuat.ac.ke)
- **Issues**: [GitHub Issues](https://github.com/Gatmach/cropai/issues)
- **Discussions**: [GitHub Discussions](https://github.com/Gatmach/cropai/discussions)

## 🗺️ Roadmap

- [x] **Phase 1**: Core AI model development
- [x] **Phase 2**: Backend API development
- [ ] **Phase 3**: Mobile app development (In Progress)
- [ ] **Phase 4**: Field testing with farmers
- [ ] **Phase 5**: Production deployment
- [ ] **Phase 6**: Integration with agricultural extension services

## 📊 Project Status

**Current Phase**: Phase 3 - Mobile App Development
**Progress**: 75% Complete
**Expected Completion**: August 2025

---

**Supporting Kenya Vision 2030 & UN SDG 2: Zero Hunger**

Made with ❤️ by the CropAI Team at JKUAT