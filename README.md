# MediParse 🩺

**My solo entry for HackNowa Global Hackathon 2026**

I built MediParse because reading lab results is stressful and most medical reports are packed with dense jargon that no regular person can understand.

MediParse is a simple Python app that lets you upload a PDF report, strips out your personal info locally so your private data doesn't get sent to random servers, and uses Gemini to translate the test results into plain, everyday English.

## What it does

* **Reads lab PDFs:** Uses `pdfplumber` to pull text out of lab reports without breaking the table structures.
* **Scrubs PII locally:** Before sending anything to the AI, a Python regex script strips out phone numbers, email addresses, dates, and ID numbers.
* **Translates jargon:** Sends the cleaned text to Gemini to get a simple, 8th-grade level summary of what was actually tested.
* **Doesn't crash:** Built in a fallback mechanism so if the API gets rate-limited or busy during testing, it doesn't just show a blank screen.

## How to run it on your machine

1. Clone the repo:

```bash
git clone https://github.com/sankett98/mediparse.git
cd mediparse

```

2. Install dependencies:

```bash
pip install -r requirements.txt

```

3. Run the Streamlit app:

```bash
streamlit run app.py

```

4. Paste your Gemini API key in the sidebar and upload a PDF lab report to test it out.

## Tech Stack

* Python 3.10+
* Streamlit (UI)
* pdfplumber (PDF text extraction)
* `re` module (regex for PII scrubbing)
* Google Gemini API (`gemini-3.8-flash`)

*Note: This project was made for a hackathon and is for educational/demo purposes only. It isn't a replacement for actual medical advice from a real doctor.*