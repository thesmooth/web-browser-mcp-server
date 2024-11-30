# Web Browser MCP Server

A Model Context Protocol (MCP) server that provides web browsing capabilities with BeautifulSoup4. This server enables structured data extraction and web page parsing, designed for seamless integration with Claude and other MCP-compatible applications.

## Integration with Claude Desktop

Add this configuration to your `claude_desktop_config.json`:

```json
{
  "mcpServers": {
    "web-browser": {
      "command": "python",
      "args": ["-m", "mcp_web_browser.cli"],
      "repository": "https://github.com/yourusername/web-browser-mcp-server",
      "env": {
        "REQUEST_TIMEOUT": "30"
      }
    }
  }
}
```

## Features

- HTML content extraction with customizable CSS selectors
- Asynchronous web page fetching
- Configurable parsing options
- Automated link discovery
- Full text extraction

## Configuration

Environment variables supported:
- REQUEST_TIMEOUT: Request timeout in seconds (default: 30)
- USER_AGENT: Custom user agent string
- MAX_RETRIES: Maximum retry attempts (default: 3)

## Development

Set up the development environment:

```bash
uv venv
source .venv/bin/activate
uv pip install -e ".[test]"
```

Run tests:
```bash
python -m pytest
```

## Security

This server implements security best practices including:
- Rate limiting
- Input validation
- Request timeouts
- Safe error handling

## License

MIT License - See LICENSE file for details