# 🇨🇳 Chinese Teacher Assistant — Real-Time Language Processing Tool 

## Overview
A multi-service backend system designed to assist language learning through real-time speech processing and vocabulary analysis.

The system processes audio input, converts it to text, and identifies unknown words for further learning.

> The idea originated from observing inefficiencies in language learning workflows, where new or unfamiliar words during conversation need to be manually tracked. The project explores how real-time processing can automate this and support more natural learning.

## Key Features
- Real-time speech-to-text processing
- Asynchronous chunk-based audio processing pipeline
- Detection of unknown vocabulary from processed text
- Integration with external ML components
- Parallel processing components implemented in Java

## Architecture & Design
The system is built using FastAPI and asynchronous processing techniques to efficiently handle continuous audio streams.

Java components are used for parallel processing tasks, improving throughput and enabling scalable handling of streaming data.

Audio data is processed in chunks to avoid blocking operations and improve responsiveness. The system coordinates multiple services across different stages of the pipeline.

Key design considerations:
- Non-blocking processing using async workflows
- Efficient handling of large and continuous audio streams
- Coordinating multiple processing stages (speech → text → analysis)

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
