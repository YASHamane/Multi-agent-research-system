# Multi-Agent Research System

A Streamlit-based research assistant that coordinates multiple AI agents
to search the web, extract useful content, draft a report, and critique
the result. The workflow separates research into stages so users can
follow how the final report is assembled.

## Features

-   **Web search:** Finds potentially relevant pages for a research
    question.
-   **Content extraction:** Collects and organizes useful information
    from selected sources.
-   **Report generation:** Produces a structured research report from
    the gathered material.
-   **Critique / review:** Runs a review stage to identify gaps and
    improve the draft.
-   **Workflow visualization:** Shows progress through the four stages
    in the Streamlit interface.
-   **Markdown export:** Lets users export the resulting report as
    Markdown.
-   **LLM-powered workflow:** Uses LangChain with GPT-4o-mini for
    language-model tasks.
-   **Search integration:** Uses Tavily for web search.

## Workflow

``` text
Research Question
       |
       v
1. Web Search Agent (Tavily)
       |
       v
2. Content Extraction Agent
       |
       v
3. Report Generation Agent (GPT-4o-mini)
       |
       v
4. Critique / Review Agent
       |
       v
Final Research Report
       |
       v
Streamlit UI / Markdown Export
```

The exact agent boundaries and tool calls depend on the implementation
in the repository.

## Technology Stack

-   **UI:** Streamlit
-   **Agent framework:** LangChain
-   **Language model:** GPT-4o-mini
-   **Web search:** Tavily
-   **Output:** Markdown report

## Getting Started

### Prerequisites

-   Python 3.10+ (or the version required by the repository)
-   Git
-   API keys for the language model and search service

### 1. Clone the repository

``` bash
git clone https://github.com/YASHamane/Multi-agent-research-system.git
cd Multi-agent-research-system
```

### 2. Create and activate a virtual environment

``` bash
python -m venv .venv
```

Windows PowerShell:

``` powershell
.venv\Scripts\Activate.ps1
```

macOS/Linux:

``` bash
source .venv/bin/activate
```

### 3. Install dependencies

``` bash
pip install -r requirements.txt
```

If the repository does not contain `requirements.txt`, install the
dependencies listed in the project configuration or create a
requirements file from the packages used by the code.

### 4. Configure API keys

Create a `.env` file if the application reads environment variables:

``` env
OPENAI_API_KEY=your_model_api_key
TAVILY_API_KEY=your_tavily_api_key
```

Use the exact variable names expected by the code. Never commit real
keys or tokens to Git.

### 5. Run the app

``` bash
streamlit run app.py
```

This assumes the Streamlit entry point is `app.py`; use the actual
entry-point filename if it differs.

## Example Use Cases

-   Build a first-pass overview of a technical topic.
-   Gather and organize information from multiple web sources.
-   Generate a structured report for further human review.
-   Export research notes into Markdown for editing or sharing.

## Limitations and Responsible Use

-   Web search results and extracted pages can be incomplete, outdated,
    or misleading.
-   Generated reports may contain unsupported claims; verify important
    facts against the original sources.
-   Follow the source websites' terms and respect copyright when storing
    or reproducing content.
-   Keep API keys in environment variables and avoid exposing them in
    logs or screenshots.
-   Treat the generated report as a research starting point, not as a
    substitute for source verification.

## Future Improvements

-   Include source links and citations alongside report claims.
-   Add retries, timeouts, and clearer handling of search/API failures.
-   Add tests for individual agents and the complete workflow.
-   Evaluate report factuality, source coverage, and critique
    usefulness.

## Author

**Yash Amane**
