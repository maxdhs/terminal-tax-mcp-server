# Installing Terminal Tax

Terminal Tax is a hosted remote MCP server. There is nothing to install, build or configure, and no API key or account.

Add one remote server with Streamable HTTP transport:

- Name: terminal-tax
- URL: https://mcp.terminal.tax/v1/hosted-mcp
- Authentication: none

Example configuration (Cline's format; other clients name the same remote server their own way, for example `"type": "http"` in a `.mcp.json`):

```json
{
  "mcpServers": {
    "terminal-tax": {
      "type": "streamableHttp",
      "url": "https://mcp.terminal.tax/v1/hosted-mcp"
    }
  }
}
```

With the Cline CLI the same server is one command:

```sh
cline mcp add terminal-tax https://mcp.terminal.tax/v1/hosted-mcp --transport streamableHttp --yes
```

To check it works, call `tools/list`; it returns create_filing_session, get_packet_schema and
continue_filing_session. Calling create_filing_session creates only an unsigned, unpaid draft: nothing is filed or charged.
The full guide for agents is https://terminal.tax/llms.txt.
