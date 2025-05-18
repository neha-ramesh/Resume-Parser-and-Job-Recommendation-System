# 📄 Smart Resume Parser

An advanced NLP-based system to parse resumes from `.pdf` format and extract structured information like Name, Email, Skills, Experience, Degree, and more.  
This tool helps HR teams and ATS systems automate resume screening with accurate data extraction and Excel report generation.

---

## 📌 Features

- 🔍 Automatically reads resumes from a folder
- 📥 Extracts:
  - Name
  - Email
  - Phone Number
  - Skills
  - Designation
  - Company Names
  - Degree(s)
  - Total Experience (calculated in years)
- 🧠 Uses **spaCy NLP** + **custom regex & keyword matching**
- 📊 Generates a clean Excel sheet with parsed results

---


## 📂 Input Format

- Resumes must be uploaded in `.pdf` format.
- Jobs database must contain job descriptions and precomputed embeddings.

---

## 🚀 Workflow

### 📝 Resume Parsing
- Extracts raw text using `pdfplumber`.
- Uses spaCy and regex to identify:

### 🧠 Job Matching
- Computes **Cosine Similarity** between resume and job description embeddings.
- Filters top 5 most relevant jobs from **different domains**.
- Prioritizes both similarity score and recency of job posting.

### 📊 Resume Scoring
- Evaluates resume structure based on ATS-friendly criteria.
- Sections scored by priority:
  - **High**: Objective, Education, Experience, Projects, Skills, Internships
  - **Medium**: Certifications, Achievements
  - **Low**: Hobbies, Interests
- Final score out of 100 with tips for improvement.

---

## 📈 Sample Output

**🔹 Top 5 Matching Jobs:**
 - Data Scientist - Lockheed Martin (⭐ 43.62%)
 - Data Analyst - RGA (⭐ 42.01%)
 - Data Engineer - Fresenius (⭐ 36.36%)
 - Network Engineer - Maruti Suzuki (⭐ 33.46%)


**📄 Resume Score:**
Your Resume Writing Score: 89/100

---

## 🛠 Technologies Used

- Python 3
- spaCy (`en_core_web_sm`)
- pdfplumber
- pandas, numpy
- scikit-learn (cosine similarity)
- dateparser

---
