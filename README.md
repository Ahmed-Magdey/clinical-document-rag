# Clinical Document Research Assistant

An educational Retrieval-Augmented Generation (RAG) project that answers questions about a clinical recommendation PDF and provides traceable source citations.

## Features

- Semantic retrieval using BGE embeddings and Chroma.
- BM25 keyword retrieval combined with semantic rankings using reciprocal rank fusion.
- Prioritization of explicitly named sections and neighboring-chunk expansion.
- Structured answers with citation-ID validation and PDF page references.
- Refusals when retrieved evidence does not support an answer.
- Gradio interface with expandable source excerpts.

## Technologies

Python, LangChain, FastEmbed, Chroma, Groq, Pandas, and Gradio.

## Run in Google Colab

1. Open `RAG_Clinical_Hybrid.ipynb` in Google Colab.
2. Run the installation cell.
3. Upload the source PDF when prompted.
4. Enter your own Groq API key through the hidden input.
5. Run the remaining cells to explore retrieval, evaluation, and the demo.

The first run downloads the embedding model. Model requests require internet access and use your Groq API allowance. The Gradio share link is temporary.

## Source Document

The project uses the 2023 USPSTF recommendation statement, “Screening for Lipid Disorders in Children and Adolescents.”

Add the official document download link here before publishing. The built-in evaluation labels apply to the specific PDF used during development.

## Evaluation

The notebook includes 20 labeled development and regression questions. Evaluation separates supporting-page retrieval from generated-answer correctness and refusal behavior.

Existing regression questions were inspected during development and are not an independent final benchmark. Page-level hits do not prove passage relevance. Citation validation checks source IDs and formatting, not factual support.

## Limitations

- Educational document research demo—not medical advice or a diagnostic tool.
- The 2023 source may not reflect current guidance.
- Designed and evaluated around one PDF.
- Extracted text, chunk boundaries, and retrieval ranking can affect answers.
- Generated claims and citations require verification.
- API failures and rate limits can interrupt requests.

## Demo

![Gradio interface](screenshots/demo.png)
