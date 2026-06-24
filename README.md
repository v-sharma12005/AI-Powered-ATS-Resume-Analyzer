#                                                                                        🤖    AI-Powered Advanced ATS Resume Analyzer

<div align="center">

[![Java](https://img.shields.io/badge/Java-21-orange?style=for-the-badge&logo=java)](https://www.java.com)
[![Spring Boot](https://img.shields.io/badge/Spring%20Boot-3.x-green?style=for-the-badge&logo=spring-boot)](https://spring.io/projects/spring-boot)
[![Spring AI](https://img.shields.io/badge/Spring%20AI-AI--Powered-blue?style=for-the-badge&logo=spring)](https://spring.io/projects/spring-ai)
[![Google Gemini](https://img.shields.io/badge/Google%20Gemini-2.5%20Flash-red?style=for-the-badge&logo=google)](https://ai.google.dev)
[![License](https://img.shields.io/badge/License-MIT-yellow?style=for-the-badge)](LICENSE)

**Transform Your Resume Into an ATS-Optimized Powerhouse** 💼

[Demo](#-quick-demo) • [Features](#-features) • [Installation](#-installation) • [API Docs](#-api-endpoints) • [Architecture](#-architecture) • [Contributing](#-contributing)

</div>

---

## 📋 About

ResumeIQ AI is an intelligent **AI-powered Applicant Tracking System (ATS) Resume Analyzer** that helps job seekers optimize their resumes for maximum ATS compatibility. Powered by **Google Gemini 2.5 Flash**, it provides actionable insights, identifies missing keywords, and generates improvement suggestions.

### Why ResumeIQ?
- ✅ **Smart Analysis**: Leverages cutting-edge AI to analyze resume compatibility
- ✅ **Actionable Insights**: Get specific, implementable recommendations
- ✅ **ATS Score**: Understand how your resume ranks against ATS systems
- ✅ **Skill Intelligence**: Identify missing skills and keywords for better placement
- ✅ **Real-time Processing**: Fast and efficient resume analysis

---

## 🚀 Features

| Feature | Description |
|---------|-------------|
| 📄 **Resume PDF Upload** | Easy drag-and-drop or file selection for PDF resumes |
| 🎯 **ATS Score Analysis** | Get a comprehensive ATS compatibility score (0-100) |
| 🔍 **Skill Extraction** | Automatically identify and list all skills mentioned in resume |
| 🔑 **Missing Keyword Detection** | Discover critical keywords missing from your resume |
| 💡 **Improvement Suggestions** | AI-powered recommendations to enhance your resume |
| 📊 **Job Description Matching** | Compare resume against job descriptions for alignment |
| 📝 **AI-Powered Summary** | Generate professional resume summaries |
| ⚡ **Real-time Processing** | Instant analysis without delays |

---

## 🛠️ Tech Stack

### Backend
- **Java 21** - Modern, high-performance language
- **Spring Boot 3.x** - Rapid application development framework
- **Spring AI** - Seamless AI integration
- **Apache Tika** - Advanced PDF text extraction
- **Maven** - Build and dependency management

### AI/ML
- **Google Gemini 2.5 Flash** - State-of-the-art LLM for analysis

### Frontend
- **HTML5** - Semantic markup
- **CSS3** - Modern styling and animations
- **JavaScript** - Interactive user experience
- **Bootstrap/Tailwind** - Responsive design (optional)

### APIs & Services
- **REST API** - RESTful architecture for clean integration
- **Google AI API** - Direct integration with Gemini

---

## 📂 Architecture

```
┌─────────────────────────────────────────────────────────────┐
│                   Frontend Layer                             │
│          (HTML/CSS/JavaScript - User Interface)             │
└────────────────────────┬────────────────────────────────────┘
                         │
                         ▼
┌─────────────────────────────────────────────────────────────┐
│              Spring Boot REST API Layer                      │
│        (Controllers, Services, Business Logic)              │
└────────────────────────┬────────────────────────────────────┘
                         │
                    ┌────┴────┐
                    ▼         ▼
         ┌──────────────┐  ┌─────────────┐
         │ Apache Tika  │  │ File Storage│
         │(PDF Parser)  │  └─────────────┘
         └──────┬───────┘
                │
                ▼
    ┌──────────────────────────────┐
    │  Spring AI ChatClient Layer   │
    │   (AI Integration & Prompts)  │
    └──────────────┬────────────────┘
                   │
                   ▼
    ┌──────────────────────────────┐
    │   Google Gemini 2.5 Flash    │
    │   (AI Analysis Engine)       │
    └──────────────────────────────┘
```

---

## ⚙️ Installation & Setup

### Prerequisites
- **Java 21** or higher
- **Maven 3.8+**
- **Google Gemini API Key** (Get it [here](https://ai.google.dev))

### Step 1: Clone Repository

```bash
git clone https://github.com/v-sharma12005/AI-ResumeAnalyser.git
cd AI-ResumeAnalyser
```

### Step 2: Configure Environment Variables

Create a `.env` file or set environment variables:

```properties
# application.properties
spring.ai.google.genai.api-key=${GEMINI_API_KEY}
spring.ai.google.genai.chat.options.model=gemini-2.5-flash
server.port=8080
```

Or set it globally:

```bash
export GEMINI_API_KEY=your-api-key-here
```

### Step 3: Build the Application

```bash
mvn clean install
```

### Step 4: Run the Application

```bash
mvn spring-boot:run
```

The application will start at `http://localhost:8080`

### Step 5: Access the Application

Open your browser and navigate to:
```
http://localhost:8080
```

---

## 📡 API Endpoints

### 1. Analyze Resume

**Endpoint:** `POST /api/resume/analyze`

**Description:** Comprehensive resume analysis with ATS score, skills, and suggestions

**Request:**
```http
POST /api/resume/analyze
Content-Type: multipart/form-data

resume: [PDF File]
jobDescription: (optional) "Job Description Text"
```

**Response:**
```json
{
  "atsScore": 82,
  "skills": ["Java", "Spring Boot", "REST API"],
  "missingKeywords": ["Kubernetes", "Docker"],
  "suggestions": [
    "Add more technical certifications",
    "Highlight leadership experience"
  ],
  "summary": "Strong technical background with expertise in backend development..."
}
```

### 2. ATS Compatibility Check

**Endpoint:** `POST /api/resume/ats-check`

**Description:** Quick ATS compatibility assessment

**Request:**
```http
POST /api/resume/ats-check
Content-Type: multipart/form-data

resume: [PDF File]
```

**Response:**
```json
{
  "isAtsCompatible": true,
  "compatibility_percentage": 85,
  "issues": [],
  "warnings": []
}
```

### 3. Skill Extraction

**Endpoint:** `POST /api/resume/extract-skills`

**Request:**
```http
POST /api/resume/extract-skills
Content-Type: multipart/form-data

resume: [PDF File]
```

**Response:**
```json
{
  "technical_skills": ["Java", "Spring", "Docker"],
  "soft_skills": ["Leadership", "Communication"],
  "tools": ["Git", "Maven"]
}
```

### 4. Health Check

**Endpoint:** `GET /api/health`

**Response:**
```json
{
  "status": "UP",
  "service": "ResumeIQ AI",
  "version": "1.0.0"
}
```

---

## 🎯 Key Features Explained

### 🔍 ATS Score Analysis
Our AI analyzes your resume against industry-standard ATS parsing algorithms to provide an accurate compatibility score. Learn what ATS systems see in your resume.

### 🎓 Skill Intelligence
Automatically identifies and categorizes skills into:
- Technical Skills
- Soft Skills
- Tools & Technologies
- Certifications

### 💼 Job Description Matching
Compare your resume directly against job descriptions to:
- Identify skill gaps
- Suggest missing keywords
- Highlight alignment areas

### 🚀 Optimization Suggestions
Get AI-powered recommendations:
- Format improvements
- Keyword optimization
- Content restructuring
- ATS-friendly formatting tips

---

## 🧪 Usage Example

### Via cURL

```bash
# Analyze a resume
curl -X POST -F "resume=@myresume.pdf" \
  http://localhost:8080/api/resume/analyze

# With job description
curl -X POST -F "resume=@myresume.pdf" \
  -F "jobDescription=Senior Java Developer..." \
  http://localhost:8080/api/resume/analyze
```

### Via JavaScript/Frontend

```javascript
const formData = new FormData();
formData.append('resume', fileInput.files[0]);
formData.append('jobDescription', jobDesc);

fetch('/api/resume/analyze', {
  method: 'POST',
  body: formData
})
.then(res => res.json())
.then(data => console.log('ATS Score:', data.atsScore));
```

---

## 📊 Sample Output

```json
{
  "resumeId": "uuid-12345",
  "atsScore": 87,
  "compatibility": {
    "formatting": "Excellent",
    "keywords": "Good",
    "structure": "Excellent"
  },
  "skills": {
    "technical": ["Java", "Spring Boot", "Microservices"],
    "soft": ["Problem Solving", "Teamwork"],
    "tools": ["Git", "Docker", "Kubernetes"]
  },
  "missing_keywords": [
    "Cloud Architecture",
    "CI/CD Pipeline",
    "API Design"
  ],
  "suggestions": [
    "Add more quantifiable achievements",
    "Include specific project outcomes",
    "Enhance technical skills section"
  ],
  "detailed_feedback": "Your resume has strong technical content but lacks metrics..."
}
```

---

## 🎯 Project Learnings

- ✅ **Spring Boot REST API Development** - Building scalable microservices
- ✅ **Spring AI Integration** - Seamless LLM integration patterns
- ✅ **Prompt Engineering** - Crafting effective AI prompts for specific tasks
- ✅ **PDF Text Extraction** - Advanced document parsing with Apache Tika
- ✅ **AI-Powered Analysis** - Implementing AI for practical use cases
- ✅ **Frontend-Backend Integration** - Full-stack development practices
- ✅ **Error Handling & Validation** - Robust error management

---

## 🚀 Performance Tips

- **Optimization**: Resume analysis typically completes in 2-5 seconds
- **Caching**: Responses are cached for identical resumes
- **Rate Limiting**: Implemented to prevent API abuse
- **Concurrent Processing**: Handle multiple requests simultaneously

---

## 🔐 Security Considerations

- ✅ API Key validation on every request
- ✅ File upload size restrictions
- ✅ Input sanitization and validation
- ✅ HTTPS recommended for production
- ✅ Secure storage of uploaded files

---

## 🤝 Contributing

Contributions are welcome! Here's how:

1. **Fork** the repository
2. **Create** a feature branch (`git checkout -b feature/AmazingFeature`)
3. **Commit** your changes (`git commit -m 'Add some AmazingFeature'`)
4. **Push** to the branch (`git push origin feature/AmazingFeature`)
5. **Open** a Pull Request

---

## 📝 Roadmap

- [ ] Support for DOCX and other formats
- [ ] Resume templates library
- [ ] Interview prep based on resume
- [ ] Cover letter generation
- [ ] Multi-language support
- [ ] Resume versioning
- [ ] Advanced analytics dashboard
- [ ] Integration with job portals

---

## 📝 License

This project is licensed under the **MIT License** - see the [LICENSE](LICENSE) file for details.

---

## 🙋 Support & Feedback

Have questions or suggestions? Feel free to:
- 💬 Open an [Issue](https://github.com/v-sharma12005/AI-ResumeAnalyser/issues)
- 📧 Contact: [GitHub Profile](https://github.com/v-sharma12005)
- 🌐 Check out more projects on my [GitHub](https://github.com/v-sharma12005)

---

## 👨‍💻 Author

<div align="center">

**Vishnu Sharma**

[![GitHub](https://img.shields.io/badge/GitHub-v--sharma12005-black?style=social&logo=github)](https://github.com/v-sharma12005)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-Connect-blue?style=social&logo=linkedin)](https://linkedin.com)
[![Email](https://img.shields.io/badge/Email-Contact-red?style=social&logo=gmail)](mailto:your-email@example.com)

</div>

---

<div align="center">

### ⭐ If you found this helpful, please consider giving it a star!

Made with ❤️ by [Vishnu Sharma](https://github.com/v-sharma12005)

</div>
