# LangChain Multi-Agent Research System

A Streamlit research assistant that combines specialized LangChain agents to search the web, extract relevant page content, write a research report, and critique the result.

## Features

- **Search agent:** Finds recent web results with Tavily.
- **Reader agent:** Fetches and extracts readable content from a selected page.
- **Writer chain:** Produces a structured report with findings and sources.
- **Critic chain:** Reviews the report and provides a score and feedback.
- **Streamlit UI:** Displays pipeline progress and results, with a Markdown download.

## Requirements

- Python 3.10 or newer
- A Google Gemini API key
- A Tavily API key

## Setup

Create and activate a virtual environment, then install the dependencies:

```powershell
py -3.10 -m venv .venv
.\.venv\Scripts\Activate.ps1
python -m pip install -r requirements.txt
```

Create a `.env` file in the project root:

```dotenv
GEMINI_API_KEY=your_gemini_api_key
TAVILY_API_KEY=your_tavily_api_key
```

Keep `.env` private; it is excluded from Git.

## Run

```powershell
streamlit run app.py
```

Enter a research topic and select **Run Research Pipeline**. The first run calls the Gemini and Tavily APIs and fetches web pages, so valid API keys and an internet connection are required.

## Project layout

```text
app.py                  Streamlit interface and pipeline orchestration
src/agents/agents.py    Search and reader agents, writer and critic chains
src/tools/tool.py      Tavily search and web-content extraction tools
src/pipelines/pipeline.py
                        Callable research pipeline for non-UI use
requirements.txt        Python dependencies
```

There is no automated test suite in the repository yet. A full live research run requires API credentials and external services.
