# Theta Health MCP Server

> Connect your Health Data to Cursor, Claude, Cherry Studio, Windsurf, and other AI assistants.

The [Model Context Protocol](https://modelcontextprotocol.io/introduction) (MCP) standardizes how Large Language Models (LLMs) talk to external services like Theta Health. It connects AI assistants directly with your Theta Health project and allows them to perform tasks like managing tables, fetching config, and querying data. See the [full list of tools](#tools).

## Setup

Configure your MCP client (such as `Cursor` / `Cherry Studio`) to use this server. Most MCP clients store the configuration as JSON in the following format:

```json
{
  "mcpServers": {
    "theta_health_mcp": {
      "url": "https://mcp.thetahealth.ai/mcp"
    }
  }
}
```

You will need to login in with `oauth2.0` for the first time.

### Claude Desktop


```json
{
  "mcpServers": {
    "theta_health_mcp": {
      "command": "npx",
      "args": [
        "-y",
        "theta_health_mcp"
      ]
    }
  }
}
```

### Claude Code

```sh
claude mcp add -s user -t http theta_health_mcp https://mcp.thetahealth.ai/mcp
```

## Tools

- **get_medical_records**: Retrieve medical records including blood tests, laboratory results and clinical measurements
- **get_functional_records**: Retrieve functional examination records including urinalysis, stool examination, pulmonary function, immunology, physical examination, ultrasound, electrocardiogram, etc.
- **get_device_data**: Retrieve device-generated health data including sleep, heart rate, blood pressure, blood oxygen, exercise, steps, etc.
- **get_user_health_profile**: Retrieve user health profile information including basic demographics, health status overview, and health data type statistics.
- **get_all_indicators**: Retrieve all available medical, functional and device indicators list with data volume and available time periods.

## Resources

- [**Model Context Protocol**](https://modelcontextprotocol.io/introduction): Learn more about MCP and its capabilities.

## License

This project is licensed under MIT. See the [LICENSE](./LICENSE) file for details.
