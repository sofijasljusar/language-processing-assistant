# 🇨🇳 Chinese Teacher Assistant — Real-Time Language Processing Tool 

## Overview
A multi-service backend system designed to assist language learning through real-time speech processing and vocabulary analysis.

The system processes audio input, converts it to text, and identifies unknown words for further learning.

> The idea originated from observing inefficiencies in language learning workflows, where new or unfamiliar words during conversation need to be manually tracked. The project explores how real-time processing can automate this and support more natural learning.

## Key Features
- Real-time speech-to-text processing
- Unknown vocabulary detection from processed text
- Asynchronous chunk-based audio processing pipeline
- Cross-language system built with Java and Python
- Producer-consumer architecture for audio processing
- Integration with ML-based transcription models (faster-whisper)

## Architecture & Design
The system consists of a Java-based audio processing service and a FastAPI transcription service:

1. **Java Recorder Service**
   * Captures microphone audio
   * Splits audio into chunks
   * Filters silent segments
   * Sends audio chunks for processing

2. **FastAPI Transcriber Service**

   * Receives audio chunks
   * Transcribes speech using Faster-Whisper
   * Segments Chinese text using Jieba
   * Detects and returns new vocabulary

**Processing Pipeline**
```text
Microphone
    ↓
Java Recorder
    ↓
FastAPI Service
    ↓
Speech-to-Text
    ↓
Word Segmentation
    ↓
Unknown Word Detection
```

**Key design considerations:**
- Non-blocking processing using async workflows
- Efficient handling of continuous audio streams
- Coordinating multiple processing stages (speech → text → analysis)
- Separation of responsibilities across independent services

## Tech Stack
- FastAPI
- asyncio
- faster-whisper
- Java

## What I Focused On
- Designing asynchronous and streaming processing pipelines
- Managing inter-service communication and data flow
- Ensuring responsiveness under continuous input

## Future improvements
- Integration of ML-based models to detect unknown words based on usage patterns
- Expand to multi-language support by leveraging the system’s modular design

## Running Locally
**Transcriber Service**
```
python -m venv venv
```

```
source venv/bin/activate
```

```
pip install -r requirements.txt
```

```
uvicorn app:app --host 127.0.0.1 --port 8000
```

Also run gui.py to see output.

**Recorder Service**

Run AudioRecorder.java and begin speaking :)
