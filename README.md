# ResumeIQ AI - ATS Resume Analyzer

An AI-powered ATS Resume Analyzer built using **Java, Spring Boot, Spring AI, and Google Gemini**. The application analyzes uploaded resumes, generates ATS scores, identifies missing skills, and provides actionable improvement suggestions.

## 🚀 Features

* Resume PDF Upload
* ATS Score Analysis
* Skill Extraction
* Missing Keyword Detection
* Resume Improvement Suggestions
* Job Description Matching
* AI-Powered Resume Summary

## 🛠️ Tech Stack

* Java 21
* Spring Boot
* Spring AI
* Google Gemini 2.5 Flash
* Apache Tika
* REST API
* HTML, CSS, JavaScript
* Maven

## 📂 Project Architecture

```text
Frontend (HTML/CSS/JS)
        ↓
Spring Boot REST API
        ↓
Apache Tika
        ↓
Spring AI ChatClient
        ↓
Google Gemini 2.5 Flash
```

## ⚙️ Setup

1. Clone Repository

```bash
git clone https://github.com/v-sharma12005/ResumeIQ-AI.git
```

2. Configure API Key

```properties
spring.ai.google.genai.api-key=${GEMINI_API_KEY}
```

3. Run Application

```bash
mvn spring-boot:run
```

## 📡 API Endpoints

### Analyze Resume

```http
POST /api/resume/analyze
```

### ATS Check

```http
POST /api/resume/ats-check
```

## 🎯 Key Learnings

* Spring Boot REST API Development
* Spring AI Integration
* Prompt Engineering
* PDF Text Extraction
* AI-Powered Resume Analysis
* Frontend-Backend Integration

## 👨‍💻 Author

**Vishnu Sharma**

GitHub: https://github.com/v-sharma12005
