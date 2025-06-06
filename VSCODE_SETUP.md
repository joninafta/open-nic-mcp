# VS Code MCP Configuration for OpenNIC Filter Context

To use this MCP server with VS Code Copilot, add the following configuration to your VS Code settings or MCP configuration file:

## Option 1: Global VS Code Settings

Add to your VS Code user settings.json:

```json
{
  "mcp.servers": {
    "opennic-filter-context": {
      "command": "node",
      "args": ["/Users/jonafta/Dev/open-nic-mcp/build/index.js"],
      "env": {}
    }
  }
}
```

## Option 2: Workspace-specific MCP Configuration

Create a `.vscode/mcp.json` file in your workspace:

```json
{
  "mcpServers": {
    "opennic-filter-context": {
      "command": "node", 
      "args": ["/Users/jonafta/Dev/open-nic-mcp/build/index.js"],
      "env": {}
    }
  }
}
```

## Option 3: Global MCP Configuration

Create or update `~/.config/mcp/mcp.json`:

```json
{
  "mcpServers": {
    "opennic-filter-context": {
      "command": "node",
      "args": ["/Users/jonafta/Dev/open-nic-mcp/build/index.js"],
      "env": {}
    }
  }
}
```

## Usage

After configuring, restart VS Code. The OpenNIC Filter Context MCP server will provide:

- **Resources**: Access to OpenNIC project documentation and requirements
- **Tools**: Simulation execution, compliance checking, and code analysis
- **Prompts**: Test scenario generation and requirements review templates

## Server Capabilities

### Resources Available:
- `opennic://filter-requirements` - Project requirements document
- `opennic://filter-implementation` - Implementation documentation  
- `opennic://register-map` - CSR register map documentation
- `opennic://simulation-guide` - Simulation setup and execution guide

### Tools Available:
- `run-filter-simulation` - Execute packet filter simulations
- `check-requirements-compliance` - Verify implementation compliance
- `analyze-filter-code` - Analyze SystemVerilog code for issues

### Prompts Available:
- `create-test-scenario` - Generate comprehensive test scenarios
