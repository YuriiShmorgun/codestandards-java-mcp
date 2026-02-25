# MCP Server

MCP Server built with FastMCP.

## Installation

```bash
python -m venv .venv
.venv\Scripts\activate
pip install --upgrade pip
pip install -r requirements.txt
```
## Run

```bash
.venv/Scripts/python.exe -m src.app
```

Or via uvicorn directly:

```bash
.venv/Scripts/python.exe -m uvicorn src.app:app --host 0.0.0.0 --port 80
```

Server starts at `http://localhost:80`. SSE endpoint: `http://localhost:80/sse`.

## Usage
