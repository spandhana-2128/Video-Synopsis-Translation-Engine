# Cross-Lingual Video Summarizer

A Flask web application offering three video/document AI tools in one platform: video dubbing into a target language, YouTube video summarization with translation, and smart document translation (PDF/Word). It helps users consume video and document content faster, or in a different language.

## Features

- **Dub Now** — Upload a video or paste a YouTube link, transcribe speech with Vosk, and dub it into a target language
- **Summarize Now** — Paste a YouTube URL to get an AI-generated summary, with an optional translated version
- **Smart Translate** — Upload a PDF or Word document and get a translated text output (via PyMuPDF / docx2txt + Google Translate)

## Tech Stack

- **Backend:** Python, Flask
- **Speech Recognition:** Vosk (`vosk-model-small-en-us-0.15`, included in the repo)
- **Translation:** `googletrans`
- **Document Parsing:** PyMuPDF (`fitz`) for PDFs, `docx2txt` for Word docs
- **Frontend:** HTML, JS, CSS (Flask templates: `index.html`, `dubnow.html`, `summarizenow.html`, `smarttranslate.html`)

## Installation

1. Clone the repository
   ```bash
   git clone https://github.com/spandhana-2128/Video-Synopsis-Translation-Engine.git
   cd Video-Synopsis-Translation-Engine
   ```

2. Create a virtual environment and install dependencies
   ```bash
   python -m venv venv
   source venv/bin/activate   # On Windows: venv\Scripts\activate
   pip install -r requirements.txt
   ```

3. The Vosk model (`vosk-model-small-en-us-0.15`) is already included in the repo — no separate download needed.

4. Run the app
   ```bash
   python app.py
   ```

5. Open `http://localhost:5000` in your browser

> Note: `requirements.txt` may not list every dependency actually imported in the code (e.g. `googletrans`, `PyMuPDF`, `docx2txt`). If you hit `ModuleNotFoundError` on a fresh install, run `pip install googletrans==4.0.0-rc1 PyMuPDF docx2txt` and add them to `requirements.txt`.

## Deployment Notes

This app requires more RAM than most free-tier hosting platforms (e.g. Render, Railway free tier) provide, due to Vosk's memory footprint during transcription. **Hugging Face Spaces** is recommended as a more suitable free hosting option for this reason.





