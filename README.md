# 🌍 Multilingual Question Answering System (Lab 4)

A voice-enabled question answering system that answers questions about documents in **English, Malayalam and French**. It reads PDFs, accepts spoken or typed questions, and reads the answers aloud.

![Python](https://img.shields.io/badge/Python-3776AB?logo=python&logoColor=white)
![Streamlit](https://img.shields.io/badge/Streamlit-FF4B4B?logo=streamlit&logoColor=white)
![Whisper](https://img.shields.io/badge/OpenAI-Whisper-412991)
![FLAN-T5](https://img.shields.io/badge/FLAN--T5-FFD21E)

## ✨ Pipeline

```
PDF documents ──▶ text extraction (PyMuPDF)
Voice question ──▶ speech-to-text (Whisper "base")
                    │
                    ├─▶ English   : FLAN-T5 answers from the English PDF
                    ├─▶ Malayalam : keyword-matched answers
                    └─▶ French    : keyword-matched answers
                    │
                    ▼
            text-to-speech (gTTS) ──▶ MP3 answers
```

The sample documents in `sample_docs/` are about the solar system.

## 🚀 Getting Started

```bash
pip install -r requirements.txt streamlit
streamlit run app.py          # web interface
```

Or run the command-line version:

```bash
python main.py                # uses question.wav if present, otherwise asks you to type a question
```

## 📂 Project Structure

```
app.py                 Streamlit interface
main.py                Command-line pipeline
models/english_qa.py   FLAN-T5 question answering
models/indic_qa.py     Malayalam answers
models/international_qa.py  French answers
utils/pdf_utils.py     PDF text extraction
utils/stt.py           Whisper speech-to-text
utils/tts.py           gTTS text-to-speech
sample_docs/           English, Malayalam and French sample PDFs
Lab4instructions.pdf   Lab brief
```
