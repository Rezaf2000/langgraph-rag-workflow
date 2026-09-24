# LangGraph RAG Workflow

A document question-answering app that uses a LangGraph state machine to combine local retrieval, relevance checks, answer generation, and a web-search fallback.

## Task and architecture

Uploaded PDF, text, Word, and spreadsheet files are processed into a Chroma-backed retriever. `RAGWorkflow` moves a question through document retrieval and relevance evaluation, conditionally routes to online search through Tavily, and generates an answer. Streamlit provides upload and Q&A views.

![Upstream workflow diagram](screenshots/graph.png)

## Repository map

| Path | Purpose |
| --- | --- |
| `app.py`, `ui_components.py` | Streamlit interface |
| `document_loader.py`, `document_processor.py`, `multimodal_loader.py` | Document ingestion |
| `rag_workflow.py`, `state.py`, `chains/` | State graph, routing, and answer chains |
| `config.py`, `.env.example` | Configuration |
| `screenshots/` | Upstream interface and workflow captures |

## Existing upstream outputs

![Upstream document interface](screenshots/document-upload.png)

![Upstream evaluation interface](screenshots/evaluations.png)

These screenshots illustrate the upstream application. The repository does not establish a newly measured benchmark for this fork. For setup and API-key configuration, see the [original README](UPSTREAM_README.md); `streamlit run app.py` is its application entry point.

## Source and license

Based on and adapted from [chitralputhran/Advanced-RAG-LangGraph](https://github.com/chitralputhran/Advanced-RAG-LangGraph). Original documentation, screenshots, code, and the [MIT license](LICENSE) are retained.