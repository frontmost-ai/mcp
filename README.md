# Frontmost AI MCP server

Frontmost AI is a headless AEO platform.
It gives your own agent the data and tools to help buyers discover and choose your business through AI.
It serves agent-run teams, one-person companies, and one-person marketing teams.

AEO means answer engine optimization. Your agent uses Frontmost AI to run your AI search strategy.
The web app remains available when you want to review results yourself.

## What your agent can do

- Review saved AI visibility results and changes over time.
- Read the answers behind those results and the sources that they cite.
- Compare the competitors that appear in those answers.
- Add, pause, resume, or update the questions that Frontmost AI tracks for your business.

These tools work with your Frontmost AI account. Your own saved results depend on your project setup and active plan or trial.
For current plans and AI app coverage, see [Frontmost AI pricing](https://frontmost.ai/pricing).

## Connect your AI

Use Frontmost AI in ChatGPT, Claude, or another MCP client that supports Streamable HTTP and OAuth sign-in.
The server runs at the hosted endpoint. You do not need to run a local server process.

### ChatGPT

Install [Frontmost AI in ChatGPT](https://chatgpt.com/plugins/plugin_asdk_app_6af5e20cbb848191837fdd2055866190) and connect your Frontmost AI account.
If you are new, complete your account and business setup when prompted.

### Claude

Open **Settings → Connectors** in Claude and add a custom connector with this URL:

```text
https://app.frontmost.ai/mcp/claude
```

Sign in with your Frontmost AI account when prompted.

### Other MCP clients

Add `https://app.frontmost.ai/mcp` as a remote Streamable HTTP server and complete OAuth sign-in.
Your client must support both the transport and authentication method.
See [Connect your AI](https://frontmost.ai/connect) for client-specific instructions.

### VS Code and GitHub Copilot

Use a VS Code configuration that supports remote HTTP MCP servers and OAuth sign-in.

1. Open the Command Palette and run **MCP: Add Server**.
2. Choose **HTTP**, enter `https://app.frontmost.ai/mcp`, and name the server `frontmost-ai`.
3. Choose the configuration location, start the server, and complete the Frontmost AI sign-in when prompted.

If you are new to Frontmost AI, complete your account and business setup when prompted.
Review the requested account access and tool actions in your client.

Current VS Code instructions: [Add and use MCP servers](https://code.visualstudio.com/docs/agent-customization/mcp-servers).

## Try a task

After connecting, ask your assistant:

> Use Frontmost AI to list my projects and review the latest saved results for my business. Show total and unbranded visibility with counts.

Then investigate an answer:

> Where did AI mention my competitors but leave my business out? Show the saved answers and their cited sources.

For a change to your tracked questions, ask:

> Add the buyer question “What are the best tools for my business category?” to my Frontmost AI project.

Use your actual category and project. Review the proposed change before confirming it in your client.
The first task starts with `list_projects`. Your agent can use `get_scan`, `get_answers`, `get_rivals`, and `get_sources` to investigate results.
Question changes use `edit_questions`.

## Registry record

- Server name: `ai.frontmost/frontmost-ai`
- Endpoint: `https://app.frontmost.ai/mcp`
- Transport: `streamable-http`
- Registry metadata: [server.json](server.json)
- [Official MCP Registry record](https://registry.modelcontextprotocol.io/v0.1/servers/ai.frontmost%2Ffrontmost-ai/versions/latest)

This repository contains the public documentation and registry metadata for the hosted Frontmost AI MCP server.

## Help

[Frontmost AI](https://frontmost.ai) · [Privacy](https://frontmost.ai/privacy) · [Terms](https://frontmost.ai/terms)

For connection help, email [hello@frontmost.ai](mailto:hello@frontmost.ai).
