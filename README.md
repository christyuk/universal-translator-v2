# 🌍 Universal Translator v2 🎙️

An end-to-end **speech translator** built with FastAPI and deployed on **Hugging Face Spaces (Docker)**.

> 🎤 Record your voice → 📝 Speech-to-Text → 🌐 Translate → 🔊 Play translation

---

## 🚀 Live Demo

> 🔗 **Hugging Face Space:**  
> https://huggingface.co/spaces/christyzenzone/universal-translator-v2

---

## ✨ Features

### 🎙️ Input

- Record audio directly in the browser
- Or upload an existing audio file (WAV / MP3 / OGG)

### 🧠 Backend

- **Whisper** for speech-to-text transcription
- **Facebook M2M100** for multi-language translation
- Language detection + translation into 100+ languages
- REST API endpoints built with **FastAPI**
- Deployed with **Uvicorn** inside a **Docker** container on Hugging Face Spaces

### 💻 Frontend

- Vanilla **HTML + CSS + JavaScript**
- Audio recording with the **MediaRecorder API**
- Dropdown to choose target language
- Shows:
  - Detected language
  - Original transcript
  - Translated text
- Clean, responsive UI

---

## 🧱 Tech Stack

**Backend**

- Python 3
- FastAPI
- Uvicorn
- Transformers (Whisper + M2M100)

**Frontend**

- HTML
- CSS
- JavaScript (Fetch + MediaRecorder API)

**Infrastructure**

- Hugging Face Spaces
- Docker
- `run.py` as application entrypoint

---

## 🔌 API Endpoints

Base path (Hugging Face): `https://christyzenzone-universal-translator-v2.hf.space/api`

- `GET /health` – simple health check
- `POST /translate_audio` – upload audio, get transcript + translation

Request (multipart form-data):

- `file`: audio file (WAV / MP3 / OGG)
- `target_lang`: language code (e.g. `es`, `fr`, `de`)

Response (JSON):

```json
{
  "detected_language": "en",
  "transcript": "Hello, how are you?",
  "translation": "Hola, ¿cómo estás?"
}
