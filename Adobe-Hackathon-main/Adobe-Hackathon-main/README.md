# Adobe-Hackathon

**Team DevGuys**  
**Members:** Gaurav Singh, Dhruv Sahni

---

##  Overview

This repository contains two distinct challenge solutions:

- **Challenge 1A – PDF Processor**: Containerized Python project for processing PDFs and extracting relevant information.
- **Challenge 1B – Persona PDF Analyzer**: A TinyLlama-based solution packaged as a standalone Docker container, tailored for persona-specific PDF analysis workflows.

---

##  Prerequisites

-  **Docker** installed on your machine
-  **Python 3.9** (for local development, if needed)

---

##  Getting Started

### Challenge 1A: PDF Processor

1. Build the Docker image using the correct platform architecture:
   ```bash
   docker build --platform linux/amd64 -t pdf-processor .
Run the container with mounted input/output directories:

bash
Copy
Edit
docker run --rm \
  -v "${PWD}/input:/app/input:ro" \
  -v "${PWD}/output:/app/output" \
  --network none \
  pdf-processor
This will process the PDFs in the input/ folder and generate results in output/.

Challenge 1B: Persona PDF Analyzer
Build the Docker image:

bash
Copy
Edit
docker build -t persona-pdf-analyzer .
Run the container, mounting required volumes:

bash
Copy
Edit
docker run --rm \
  -v "${PWD}/input_jsons:/app/input_jsons" \
  -v "${PWD}/input_pdfs:/app/input_pdfs" \
  -v "${PWD}/outputs:/app/outputs" \
  -v "${PWD}/tinyllama_model:/app/tinyllama_model" \
  persona-pdf-analyzer
Directory Layout
bash
Copy
Edit
Adobe-Hackathon/
│
├── Challenge-1A/               # PDF-Processor solution
│
├── challenge1b_tinyllama_full/ # Persona PDF Analyzer
│
└── README.md                   # Project overview and instructions
Tips & Notes
Ensure terminal is opened at the relevant directory before building or running each challenge.

Use backticks (`) around the Docker run command to ensure it executes as a single line in PowerShell/Windows terminals.

--network none flag isolates the container from external networks—great for security.
