A web application that takes YouTube videos and generates concise summaries along with dubbed audio in a target language. Built with Flask and powered by speech recognition and AI summarization, it helps users quickly grasp video content without watching the full length, or consume it in a different language.

Features


YouTube Video Input — Accepts a YouTube URL and processes the video/audio
Speech-to-Text — Transcribes spoken audio using Vosk
AI Summarization — Condenses transcribed content into a short, readable summary
Audio Dubbing — Converts and dubs the summarized/translated content into a target language
Web Interface — Simple Flask-based UI for submitting videos and viewing/listening to results


Tech Stack


Backend: Python, Flask
Speech Recognition: Vosk
Summarization/Translation: AI/NLP models
Frontend: HTML, CSS, JS (Flask templates)


Installation


Clone the repository


bash   git clone https://github.com/yourusername/your-repo-name.git
   cd your-repo-name


Create a virtual environment and install dependencies


bash   python -m venv venv
   source venv/bin/activate   # On Windows: venv\Scripts\activate
   pip install -r requirements.txt


Download the required Vosk model and place it in the appropriate directory (see /models or update path in config)
Run the app


bash   python app.py


Open http://localhost:5000 in your browser


Deployment Notes

This app requires more RAM than most free-tier hosting platforms (e.g. Render, Railway free tier) provide, due to Vosk's memory footprint during transcription. Hugging Face Spaces is recommended as a more suitable free hosting option for this reason.

Usage


Paste a YouTube video URL into the input field
Wait for the app to transcribe, summarize, and dub the content
View the summary and play/download the dubbed audio
