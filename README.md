# Text Summarizer (T5 Transformer)

This is a simple text summarizer web app built with FastAPI. It uses a fine-tuned HuggingFace `t5-small` transformer model to take long pieces of text and shrink them down into a quick summary.

## Features

- **Transformer Model:** Uses the `t5-small` model for natural, abstractive summarizations.
- **FastAPI Backend:** Super fast and clean Python backend.
- **Minimal UI:** Easy to use interface.

## Project Structure

```bash
Text_Summarizer
├── app.py                     # Main FastAPI application & API Endpoints
├── requirements.txt           # Python dependencies
├── .gitignore                 # Files/folders ignored by git
├── saved_summary_model        # Local weights/config of the T5 model
├── static
│   └── style.css              # Dark gold theme stylesheet
└── templates
    └── index.html             # The front-end view
```

## Setup & Running Locally

1. **Clone the repository and set up environment:**
   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows use: venv\Scripts\activate
   ```

2. **Install Required Packages:**
   ```bash
   pip install -r requirements.txt
   ```

3. **Start the server:**
   Ensure you're inside the root directory where `app.py` is located.
   ```bash
   uvicorn app:app --reload
   ```

4. **Open in Browser:**
   Visit `http://localhost:8000` to interact with the UI.

