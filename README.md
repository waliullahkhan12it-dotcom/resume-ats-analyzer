# 📄 Resume ATS Analyzer

An AI-powered Streamlit application that analyzes a resume and provides an estimated ATS-readiness score, strengths, ATS warnings, keyword gaps, and actionable improvement suggestions.

## Features

- Upload PDF or DOCX resumes
- Extract resume text
- Optional job-description matching
- AI-powered ATS-readiness score from 0–100
- Section-by-section scores
- Missing/weak keyword suggestions
- ATS warnings
- Resume improvement recommendations
- Rewrite examples for weak resume content
- Download the analysis as JSON

## Tech Stack

- Python
- Streamlit
- Google Gemini API (`gemini-2.5-flash`)
- PyPDF
- python-docx

## Project Structure

```text
resume-ats-analyzer/
├── app.py
├── requirements.txt
└── README.md
```

## Run Locally

### 1. Install dependencies

```bash
pip install -r requirements.txt
```

### 2. Get a Gemini API key

Create a Gemini API key from Google AI Studio.

### 3. Start the app

```bash
streamlit run app.py
```

The app will open in your browser.

## Gemini API Key

You can enter the key in the app sidebar.

For Streamlit Community Cloud, add the key as a secret named:

```text
GEMINI_API_KEY
```

Do **not** commit your real API key to GitHub.

## Important ATS Note

The score is an AI-based estimate, not an official score from a particular ATS vendor. Different applicant-tracking systems use different parsing and ranking rules.

The optional job description makes the keyword analysis more targeted.

## Supported Resume Files

- PDF
- DOCX

Scanned/image-only PDFs may not produce useful extracted text.

## Deployment

This project is designed for Streamlit Community Cloud.

1. Push `app.py`, `requirements.txt`, and `README.md` to a GitHub repository.
2. Sign in to Streamlit Community Cloud with GitHub.
3. Create a new app and select the repository.
4. Set the main file to `app.py`.
5. Add `GEMINI_API_KEY` in the app's Secrets settings.
6. Deploy.

## Security

- Never hard-code your Gemini API key.
- Never commit `.env` files containing secrets.
- Resume data is processed by the application and sent to Gemini for analysis.
- Avoid uploading resumes containing information you do not want processed by a third-party AI service.

## Disclaimer

This tool provides career-support suggestions and an estimated ATS-readiness score. It does not guarantee interviews, job offers, or compatibility with every ATS.
