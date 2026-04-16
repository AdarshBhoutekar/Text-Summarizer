# Text Summarizer (T5 Transformer)

This project is a text summarization web application built with FastAPI, Jinja2, and a fine-tuned Hugging Face `t5-small` model. It accepts long-form input text, cleans it, runs transformer-based inference, and returns a shorter abstractive summary through both a browser UI and a REST API.

## Live Demo

https://text-summarizer-fzug.onrender.com/

## Project Overview

The goal of this project is to make long text easier to understand quickly. Instead of extracting a few lines directly from the original content, the model generates a new condensed version that captures the main meaning in fewer words.

This repository includes:

- A FastAPI backend for serving the model
- A simple web interface for entering text and viewing summaries
- A local saved transformer model inside `saved_summary_model`
- Basic preprocessing and device selection for CPU, CUDA, or Apple MPS

## Key Features

- Transformer-based abstractive summarization using a fine-tuned `t5-small` model
- FastAPI application with a clean API endpoint
- Browser-based frontend using Jinja2 templates and static CSS
- Automatic device selection for `cpu`, `cuda`, or `mps`
- Local model loading from the repository without needing to download model weights at runtime

## How It Works

1. The user enters or pastes text into the web interface.
2. The frontend sends the text to the `/summarize/` endpoint as JSON.
3. The backend cleans the input by removing extra whitespace and HTML tags.
4. The tokenizer converts the text into model inputs.
5. The T5 model generates a summary using beam search.
6. The generated tokens are decoded and returned to the user.

## Tech Stack

- Python `3.10.20`
- FastAPI
- Uvicorn
- Hugging Face Transformers
- PyTorch
- Jinja2
- HTML, CSS, and vanilla JavaScript

## Project Structure

```text
Text_Summarizer/
|-- app.py                  # FastAPI app, model loading, preprocessing, and routes
|-- requirements.txt        # Python dependencies
|-- saved_summary_model/    # Fine-tuned T5 model files and tokenizer assets
|-- static/
|   `-- style.css           # Frontend styling
`-- templates/
    `-- index.html          # Main UI template
```

## Running Locally

Python version required: **3.10.20**

1. Clone the repository:

   ```bash
   git clone https://github.com/AdarshBhoutekar/Text-Summarizer.git
   cd Text-Summarizer
   ```

2. Create a Conda environment:

   ```bash
   conda create -n txtsum python=3.10.20
   ```

3. Activate the Conda environment:

   ```bash
   conda activate txtsum
   ```

4. Verify the Python version:

   ```bash
   python --version
   ```

   It should print `Python 3.10.20`.

5. Install required packages:

   ```bash
   pip install -r requirements.txt
   ```

6. Start the development server:

   ```bash
   uvicorn app:app --reload
   ```

7. Open the app in your browser:

   ```text
   http://localhost:8000
   ```

## Example Use Cases

- Summarizing articles, blogs, or reports
- Reducing long written content into quick notes
- Testing a fine-tuned transformer model in a web app
- Demonstrating NLP deployment with FastAPI

## Notes

- The application loads the model from the local `saved_summary_model` folder.
- Summary quality depends on the data used during fine-tuning and the length or style of the input text.
- Very long inputs are truncated during tokenization because the model uses a fixed maximum input length.
