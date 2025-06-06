# OpenNIC Packet Filter MCP Server

A Model Context Protocol (MCP) server for managing context and operations related to the OpenNIC packet filter project. This server provides access to project documentation, simulation tools, and compliance checking for the hardware implementation.

## Features

### Resources
- **Filter Requirements**: Access to complete requirements specification
- **Implementation Documentation**: Detailed SystemVerilog implementation guide  
- **Register Map**: Control and Status Register specifications
- **Simulation Guide**: Cocotb testbench setup and execution instructions

### Tools
- **run-filter-simulation**: Execute packet filter simulations with various configurations
- **check-requirements-compliance**: Verify implementation meets specified requirements
- **analyze-filter-code**: Analyze SystemVerilog code for potential issues

### Prompts
- **create-test-scenario**: Generate comprehensive test scenarios for validation

## Installation

1. Clone or download this repository
2. Install dependencies:
   ```bash
   npm install
   ```
3. Build the TypeScript code:
   ```bash
   npm run build
   ```

## Usage

### VS Code Integration

1. Add the following to your VS Code `mcp.json` configuration:
   ```json
   {
     "mcpServers": {
       "opennic-filter-context": {
         "command": "node",
         "args": ["/path/to/open-nic-mcp/build/index.js"],
         "env": {}
       }
     }
   }
   ```

2. Restart VS Code to load the MCP server

### Standalone Usage

Run the server directly:
```bash
npm start
```

The server communicates via stdio and follows the MCP protocol specification.

## Development

### Project Structure
```
open-nic-mcp/
├── src/
│   └── index.ts          # Main server implementation
├── build/                # Compiled JavaScript output
├── package.json          # Node.js dependencies and scripts  
├── tsconfig.json         # TypeScript configuration
└── mcp.json             # VS Code MCP configuration
```

### Building
```bash
npm run build
```

### Development Mode
```bash
npm run dev
```

## OpenNIC Project Context

This MCP server is specifically designed to work with the OpenNIC packet filter project, providing context for:

- **Hardware Description**: SystemVerilog implementation of packet filtering
- **Verification Environment**: Cocotb-based testbenches and simulation
- **Requirements Management**: Compliance checking and validation
- **Documentation Access**: Centralized access to project documentation

### Expected Project Structure
The server expects the OpenNIC project to be located at:
```
/Users/jonafta/Dev/open-nic-shell-ji-mb/
├── requirements.md                              # Project requirements
├── opennic_packet_filter_submission.md         # Implementation documentation
├── plugin/p2p/box_250mhz/
│   ├── filter_rx_pipeline/src/                 # SystemVerilog source
│   └── csr/doc/register_map.md                 # Register documentation
└── tb/tests/filter_rx_pipeline/                # Test environment
```

## Contributing

1. Make changes to `src/index.ts`
2. Build with `npm run build`
3. Test the server functionality
4. Submit pull requests with clear descriptions

## License

ISC License - see package.json for details.

## Support

For issues related to the OpenNIC packet filter implementation or MCP server functionality, please refer to the project documentation or open an issue.
