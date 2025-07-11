 # FixMate: Multilingual Voice Assistant for Appliance Troubleshooting




## Steps to run the project - run the commands in terminal

1. Unzip the folder
2. run -> pip install -r requirements.txt
3. run -> streamlit run main.py


## Overview

FixMate is a real-time, voice-first virtual assistant designed to help users troubleshoot consumer appliances (e.g., washing machines) through natural, multilingual conversations. Powered by Retrieval-Augmented Generation (RAG), it extracts relevant information from user manuals and delivers spoken responses in the user’s language. The assistant features real-time speech input, automatic language detection, LLM-powered response generation, and avatar-based video replies, offering a seamless and human-like support experience.



## Objectives

- **Voice-First Interaction:** Users can ask troubleshooting questions by speaking naturally in any supported language (e.g., English, Japanese, Chinese, Hindi).
- **Accurate Retrieval:** Employ RAG techniques to search and extract relevant manual sections for user queries.
- **Multilingual Understanding:** Detect spoken language, process queries, and generate responses in the same language.


## Key Features

- **Voice Input (ASR):**  
  Uses microphone input and `speech_recognition` to capture and transcribe user queries.

- **Language Detection:**  
  Auto-detects spoken language using `langdetect`.

- **Semantic Search (RAG):**  
  Converts manuals into embeddings using `SentenceTransformers` and retrieves relevant chunks for each query.

- **LLM Response Generation:**  
  Uses Google Gemini (1.5 Flash) to generate context-aware answers.

- **Text-to-Speech (TTS):**  
  Converts text responses to speech using `gTTS`.

- **Avatar Video Generation:**  
  Uses the D-ID API to generate an AI avatar that speaks the answer with lip-sync animation.

## Tools Explored (But Not Used in Final Build)
- LangChain, ChromaDB, Pinecone (for advanced RAG)
- Whisper, Vosk (ASR)
- Coqui TTS, ElevenLabs (TTS alternatives)

## Tech Stack

**Language:** Python  
**Frontend:** Streamlit  
**Libraries:** SentenceTransformers, langdetect, gTTS, PyPDF2, speech_recognition  
**APIs:** Gemini 1.5 Flash, D-ID API  



## Benefits

- **24/7 On-Demand Support:** Users receive instant guidance without waiting for a human technician.
- **User Satisfaction:** A natural conversational interface increases accessibility and ease of use.

---

## Steps to Start the Application

### 1. Data Collection
- Gather user manuals for various consumer products in multiple languages.

### 2. Simple Text RAG
- Implement a basic RAG pipeline:
  - User inputs a text query.
  - System retrieves and responds in text.
- Tools: [LangChain](https://python.langchain.com/), [ChromaDB](https://www.trychroma.com/), [Pinecone](https://www.pinecone.io/), [OpenAI Embeddings](https://platform.openai.com/docs/guides/embeddings).

### 3. Integrate Free ASR and TTS APIs
- Research and select free/open-source tools for ASR and TTS:
  - **ASR:** [OpenAI Whisper](https://github.com/openai/whisper), [Vosk](https://alphacephei.com/vosk/).
  - **TTS:** [Coqui TTS](https://github.com/coqui-ai/TTS), [Google Cloud TTS (free tier)](https://cloud.google.com/text-to-speech), [ElevenLabs](https://elevenlabs.io/).

### 4. Voice Output RAG
- Extend text RAG to output responses as voice using a TTS engine.

### 5. Voice Input RAG
- Enable voice queries using ASR.
- Process spoken questions and respond with both text and voice.

### 6. Multilingual Response Logic
- Detect user’s spoken language automatically.
- Ensure the system replies in the same language as the input.

---

## Usage Flow

1. **User**: Speaks a troubleshooting question in their language
2. **System**:  
   a. Captures and transcribes the speech (ASR + Language ID) 
   b. Searches manuals for relevant troubleshooting steps (RAG) 
   c. Generates a concise answer (LLM)
   d. Converts the answer to speech (TTS)

