# mcp

Model Context Protocol (MCP) Server for the *mcp* API.

<div align="left">
    <a href="https://www.speakeasy.com/?utm_source=mcp&utm_campaign=mcp-typescript"><img src="https://www.speakeasy.com/assets/badges/built-by-speakeasy.svg" /></a>
    <a href="https://opensource.org/licenses/MIT">
        <img src="https://img.shields.io/badge/License-MIT-blue.svg" style="width: 100px; height: 28px;" />
    </a>
</div>


<br /><br />
> [!IMPORTANT]
> This MCP Server is not yet ready for production use. Delete this notice before publishing to a package manager.

<!-- Start Summary [summary] -->
## Summary


<!-- End Summary [summary] -->

<!-- Start Table of Contents [toc] -->
## Table of Contents
<!-- $toc-max-depth=2 -->
* [mcp](#mcp)
  * [Installation](#installation)
  * [Development](#development)
  * [Contributions](#contributions)

<!-- End Table of Contents [toc] -->

<!-- Start Installation [installation] -->
## Installation

> [!TIP]
> To finish publishing your MCP Server to npm and others you must [run your first generation action](https://www.speakeasy.com/docs/github-setup#step-by-step-guide).

Deployed at https://cloudinary-test-mcp-server.kanwar-a2e.workers.dev
<details>
<summary>DXT (Desktop Extension)</summary>

Install the MCP server as a Desktop Extension using the pre-built [`mcp-server.dxt`](./mcp-server.dxt) file:

Simply drag and drop the [`mcp-server.dxt`](./mcp-server.dxt) file onto Claude Desktop to install the extension.

The DXT package includes the MCP server and all necessary configuration. Once installed, the server will be available without additional setup.

> [!NOTE]
> DXT (Desktop Extensions) provide a streamlined way to package and distribute MCP servers. Learn more about [Desktop Extensions](https://www.anthropic.com/engineering/desktop-extensions).

</details>

<details>
<summary>Cursor</summary>

[![Install MCP Server](https://cursor.com/deeplink/mcp-install-dark.svg)](https://cursor.com/install-mcp?name=SDK&config=eyJtY3BTZXJ2ZXJzIjp7IlNESyI6eyJ0eXBlIjoibWNwIiwidXJsIjoiaHR0cHM6Ly9jbG91ZGluYXJ5LXRlc3QtbWNwLXNlcnZlci5rYW53YXItYTJlLndvcmtlcnMuZGV2L21jcCIsImhlYWRlcnMiOnsieC1jbG91ZGluYXJ5LWF1dGgiOiIke01DUF9DTE9VRElOQVJZX0FVVEh9IiwieC1vYXV0aDIiOiIke01DUF9PQVVUSDJ9In19fX0=)

Or manually:

1. Open Cursor Settings
2. Select Tools and Integrations
3. Select New MCP Server
4. If the configuration file is empty paste the following JSON into the MCP Server Configuration:

```json
{
  "mcpServers": {
    "SDK": {
      "type": "mcp",
      "url": "https://cloudinary-test-mcp-server.kanwar-a2e.workers.dev/mcp",
      "headers": {
        "x-cloudinary-auth": "${MCP_CLOUDINARY_AUTH}",
        "x-oauth2": "${MCP_OAUTH2}"
      }
    }
  }
}
```

</details>

<details>
<summary>Claude Code CLI</summary>

```bash
claude mcp add --transport sse SDK https://cloudinary-test-mcp-server.kanwar-a2e.workers.dev/sse --header "x-cloudinary-auth: ..." --header "x-oauth2: ..."
```

</details>
<details>
<summary>Windsurf</summary>

Refer to [Official Windsurf documentation](https://docs.windsurf.com/windsurf/cascade/mcp#adding-a-new-mcp-plugin) for latest information

1. Open Windsurf Settings
2. Select Cascade on left side menu
3. Click on `Manage MCPs`. (To Manage MCPs you should be signed in with a Windsurf Account)
4. Click on `View raw config` to open up the mcp configuration file.
5. If the configuration file is empty paste the full json
```
{
  "mcpServers": {
    "SDK": {
      "type": "mcp",
      "url": "https://cloudinary-test-mcp-server.kanwar-a2e.workers.dev/mcp",
      "headers": {
        "x-cloudinary-auth": "${MCP_CLOUDINARY_AUTH}",
        "x-oauth2": "${MCP_OAUTH2}"
      }
    }
  }
}
```
</details>
<details>
<summary>VS Code</summary>

Refer to [Official VS Code documentation](https://code.visualstudio.com/api/extension-guides/ai/mcp) for latest information

1. Open [Command Palette](https://code.visualstudio.com/docs/getstarted/userinterface#_command-palette)
1. Search and open `MCP: Open User Configuration`. This should open mcp.json file
2. If the configuration file is empty paste the full json
```
{
  "servers": {
    "SDK": {
      "type": "mcp",
      "url": "https://cloudinary-test-mcp-server.kanwar-a2e.workers.dev/mcp",
      "headers": {
        "x-cloudinary-auth": "${env:MCP_CLOUDINARY_AUTH}",
        "x-oauth2": "${env:MCP_OAUTH2}"
      }
    }
  }
}
```

</details>


<details>
<summary> Stdio installation via npm </summary>
To start the MCP server, run:

```bash
npx mcp start --api-key ... --api-secret ... --oauth2 ... --cloud-name ...
```

For a full list of server arguments, run:

```
npx mcp --help
```

</details>
<!-- End Installation [installation] -->

<!-- Placeholder for Future Speakeasy SDK Sections -->

## Development

Run locally without a published npm package:
1. Clone this repository
2. Run `npm install`
3. Run `npm run build`
4. Run `node ./bin/mcp-server.js start --api-key ... --api-secret ... --oauth2 ... --cloud-name ...`
To use this local version with Cursor, Claude or other MCP Clients, you'll need to add the following config:

```json
{
  "mcpServers": {
    "SDK": {
      "command": "node",
      "args": [
        "./bin/mcp-server.js",
        "start",
        "--api-key",
        "...",
        "--api-secret",
        "...",
        "--oauth2",
        "...",
        "--cloud-name",
        "..."
      ]
    }
  }
}
```

Or to debug the MCP server locally, use the official MCP Inspector: 

```bash
npx @modelcontextprotocol/inspector node ./bin/mcp-server.js start --api-key ... --api-secret ... --oauth2 ... --cloud-name ...
```



## Contributions

While we value contributions to this MCP Server, the code is generated programmatically. Any manual changes added to internal files will be overwritten on the next generation. 
We look forward to hearing your feedback. Feel free to open a PR or an issue with a proof of concept and we'll do our best to include it in a future release. 

### MCP Server Created by [Speakeasy](https://www.speakeasy.com/?utm_source=mcp&utm_campaign=mcp-typescript)
