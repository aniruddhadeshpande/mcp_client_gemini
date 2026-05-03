# MCP Client Gemini

A small interactive MCP client that connects to an MCP server over stdio and lets Gemini call the server's tools.

The client:

- starts a Python or Node MCP server script passed on the command line
- lists the tools exposed by that server
- converts MCP tool schemas into Gemini function declarations
- opens an interactive prompt where Gemini can answer directly or call MCP tools

## Requirements

- Python 3.13 or newer
- A Gemini API key
- An MCP server script to connect to

## Setup

Install dependencies:

```bash
uv add install -r requirements.txt
```

Create a `.env` file in this project directory and add your Gemini API key:

```env
GEMINI_API_KEY=your_api_key_here
```

## Use The MCP Client

Run the client with the MCP server script path:

```bash
python client.py ../mcp_basic/main.py
```

After the client connects, it prints the available MCP tools and starts an interactive chat:

```text
MCP Client Started! Type 'quit' to exit.

Query:
```

Type a question or instruction at the prompt. Type `quit` to close the session.

## General Usage

You can point the client at any supported MCP server script:

```bash
python client.py <path_to_server_script>
```

If the server path ends with `.py`, the client starts it with `python`. Otherwise, it starts it with `node`.
