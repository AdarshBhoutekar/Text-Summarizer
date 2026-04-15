# Text Summarizer (T5 Transformer)

This is a simple text summarizer web app built with FastAPI. It uses a fine-tuned HuggingFace `t5-small` transformer model to take long pieces of text and shrink them down into a quick summary.

## Live Demo :
https://text-summarizer-fzug.onrender.com/

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

Python version required: **3.10.20**

1. **Clone the repository:**
   ```bash
   git clone https://github.com/AdarshBhoutekar/Text-Summarizer.git
   cd Text-Summarizer
   ```

2. **Create a virtual environment (Python 3.10.20):**
   ```bash
   # Windows (uses installed Python 3.10.x)
   py -3.10 -m venv venv

   # Windows (exact interpreter path for 3.10.20)
   # Example:
   # "C:\\Users\\<you>\\AppData\\Local\\Programs\\Python\\Python310\\python.exe" -m venv venv

   # macOS/Linux (ensure this points to Python 3.10.20)
   python3.10 -m venv venv
   ```

3. **Activate the virtual environment:**
   ```bash
   # Windows (PowerShell)
   .\venv\Scripts\Activate.ps1

   # Windows (CMD)
   venv\Scripts\activate.bat

   # macOS/Linux
   source venv/bin/activate
   ```

4. **Verify Python version:**
   ```bash
   python --version
   ```
   It should print Python 3.10.20.

5. **Install required packages:**
   ```bash
   pip install -r requirements.txt
   ```

6. **Start the development server:**
   ```bash
   uvicorn app:app --reload
   ```

7. **Open in browser:**
   Visit http://localhost:8000

