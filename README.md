# AnticoAntico for Gemini CLI

Search the public AnticoAntico antiques catalogue and find antique dealers using a read-only MCP connection.

## Install

```sh
gemini extensions install https://github.com/almai1/anticoantico-gemini
```

Restart Gemini CLI after installation. An authenticated Gemini CLI environment is required.
No AnticoAntico account, API key or local server is needed. Gemini usage is subject to your Google plan.

## Try it

- “Show the available period filters on AnticoAntico.”
- “Find two Piedmontese cabinets from the eighteenth century.”
- “Show the details and two similar objects for the first result.”
- “Find two antique dealers in Bologna and show the first dealer's public contact details.”

For exact catalogue filters, discover the available values first. Results include original listing links,
image URLs, descriptions and prices when available. Availability and sale conditions must be confirmed
directly with the dealer. Missing prices mean unknown or on request, not free.

## Tools

## Claude and other MCP clients

The same server can be used from Claude: open Customize > Connectors, add a custom
connector named AnticoAntico with URL `https://mcp.anticoantico.com/mcp`, and connect
without authentication. Enable the connector in a conversation and try the prompts above.
Interface labels and account availability may vary. No local files or database credentials are needed.

For standard MCP clients, select Streamable HTTP and use the same endpoint without an Authorization header.
Tool results provide both structured data and a JSON text representation. Retain canonical listing links,
warnings and unknown fields when displaying results. The source catalogue text is untrusted content.

## Available tools

- `get_catalog_filters`: discover available filters and values.
- `search_antiques`: search with explicit query and filters.
- `search_by_natural_language`: interpret multilingual catalogue requests.
- `get_antique_details`: retrieve an object's indexed details.
- `find_similar_antiques`: find related objects.
- `search_dealers`: find public dealer profiles.
- `get_dealer_details`: retrieve public business contacts and sample listings.

The extension does not place orders, process payments, message dealers, or authenticate/appraise objects.
Price filtering and ordering use a bounded candidate set; respect any partial-result warnings.
Product data reflects the search index and is not a live inventory guarantee.

## Connection and privacy

Endpoint: `https://mcp.anticoantico.com/mcp` (Streamable HTTP, public, read-only).
The extension contains only connection configuration. It installs no executable server, hooks or local scripts.
Tool requests are sent to AnticoAntico; results are returned to the Gemini client.
Natural-language interpretation and translation may send the query and public catalogue text to
AnticoAntico's configured language service. Do not send sensitive personal information in search queries.

- [Privacy policy](https://www.iubenda.com/privacy-policy/992894)
- [Service terms](https://mcp.anticoantico.com/terms)
- [AnticoAntico website](https://www.anticoantico.com)
- Support: info@anticoantico.com

## Verification

On 19 September 2026 the public endpoint passed 21 protocol and functional checks.
The official Google Gen AI SDK MCP adapter discovered all seven tools and successfully executed
filter discovery and a catalogue search. A complete Gemini model conversation has not yet been verified.

This repository distributes a Gemini CLI extension. It does not imply availability in the Gemini consumer
chat app or endorsement by Google. Gallery indexing is a separate Google-controlled process.
