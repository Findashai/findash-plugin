# Findash plugin

Connect Cursor and Grok Bot to [Findash](https://findash.ai) through Findash's hosted Model Context Protocol (MCP) server.

## What it provides

The connector exposes tools for client and prospect records, financial planning information, tasks, notes, calendar events, and workflows. Available tools and records depend on the signed-in user's Findash role, permissions, and OAuth consent.

## Requirements

- An active Findash account with access to the records you want to use.
- A compatible MCP client with remote HTTP and OAuth support.
- Permission from your organization to connect the service, where applicable.

## Connect

This repository is submitted for marketplace review; a public listing is not yet approved.

Until the listing is available, add a custom remote MCP server in your client using:

```text
https://findash.ai/api/ai/mcp
```

For a client that accepts `mcp.json`, use the configuration in this repository. Authenticate through the client's Authorize action and sign in to Findash. Review the requested access before approving it. Do not paste passwords, access tokens, or authorization codes into chat.

Findash recognizes the exact Cursor web, Grok Bot cloud, and desktop callback URLs documented for this integration. If registration reports `redirect_uri not allowlisted on this server`, contact support with the callback URL from `details.disallowed` and your client version. Do not send tokens or authorization codes. Marketplace submission alone does not enable callback compatibility.

## Example requests

- Find the client record for a person I name.
- Summarize my outstanding client tasks.
- Show recent notes and upcoming meetings for a selected client.
- Draft a task update, then ask me before saving it.

## Authentication and data access

The server uses OAuth authorization code flow with PKCE. Each person signs in with their own Findash account. The plugin contains no credentials and does not grant access by itself. Findash enforces user and firm access controls. Tools may change records when the connected user has permission; review your client's tool settings and authorize changes deliberately.

The connector sends requested tool inputs and results between your MCP client and Findash. Review your client's data handling policies before connecting sensitive information. Findash's current policies are available on [findash.ai](https://findash.ai).

## Support

Email [hello@findash.ai](mailto:hello@findash.ai) for connection issues. Report only the client version, callback URL, error text, and approximate failure time, without credentials or private client records.

## License

The connector configuration and documentation are MIT licensed. Access to the hosted Findash service is governed by its own terms. The logo remains a FinDash brand asset; the license does not grant trademark rights.
