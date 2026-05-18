# KnightTech WW2 Memoir RAG

> Look what AI can help preserve.

AI-assisted historical preservation using OCR, human review, Azure AI Search, Azure OpenAI, and a custom Azure-hosted Flask UI.

This project is a working MVP that uses Retrieval-Augmented Generation (RAG) to preserve and query the WWII memoir and related historical materials of Walter Knight. The goal was not to build another generic chatbot, but to use AI to help preserve a family story, historical context, and personal legacy through grounded retrieval.

---

## Project Purpose

This project was built around a simple idea:

**Technology matters most when it helps preserve what makes us human.**

The source material included historical documents, OCR-processed text, article content, and reviewed memoir material. The final MVP allowed a user to ask questions through a custom KnightTech web interface and receive answers grounded in the indexed source material.

The project focused on:

- Historical preservation
- AI for good
- OCR and human-in-the-loop review
- Grounded retrieval from source documents
- Responsible AI behavior
- Custom Azure-hosted deployment

---

## Header / Project Visual

![KnightTech WW2 Memoir Header](images/knight-header-pic.png)

---

## Current MVP Architecture

![Current MVP Architecture](images/current-mvp-architecture.png)

The current MVP used a single Azure App Service running a custom Flask application. The Flask app handled both the frontend UI and backend logic. User questions were submitted through the KnightTech interface and processed server-side using Azure OpenAI and Azure AI Search.

High-level flow:

```text
User Browser
    ↓ HTTPS
Azure App Service
    ↓ Flask backend
Azure OpenAI GPT-4o
    ↓ Grounding / retrieval
Azure AI Search
    ↓ Indexed source material
Azure Blob Storage / OCR-processed documents
