---
name: paperless-ngx-connector
description: Connect to a Paperless-ngx instance via its REST API for document ingestion, search, metadata updates, and administration tasks. Use when a user asks to authenticate to Paperless-ngx, upload or index documents, list/search documents, manage tags/correspondents/document types, or automate Paperless-ngx workflows from an assistant.
---

# Paperless Ngx Connector

## Overview

Connect to Paperless-ngx using its REST API with an API token and base URL. Use this skill to authenticate, validate connectivity, and perform document-centric operations (upload, search, update metadata) while following the official API docs.

## Workflow

### 1) Collect configuration

Gather the minimum config before making calls:

- `PAPERLESS_BASE_URL` (e.g., `https://paperless.example.com`)
- `PAPERLESS_API_TOKEN` (user API token)
- Optional: `PAPERLESS_VERIFY_SSL` (true/false) if the instance uses custom TLS

If the user does not know their token or base URL, ask for them. Do not guess.

### 2) Validate connectivity

Confirm the instance is reachable and the token is valid.

- Use the API docs to confirm the exact auth header (commonly `Authorization: Token <token>`).
- Start with a simple GET endpoint (e.g., list documents) to verify authentication.

### 3) Execute the requested task

Use the official API reference to pick endpoints and payloads. Typical tasks include:

- Uploading documents with metadata (tags, correspondent, document type, storage path)
- Searching or filtering documents
- Updating document metadata
- Listing tags/correspondents/document types

When in doubt, read `references/paperless-ngx-api.md` and then consult the official docs.

### 4) Handle errors and confirm results

- Surface HTTP status codes and validation errors
- If an upload is asynchronous, poll or re-fetch to confirm the document state
- Keep secrets out of logs and outputs

## Resources

### references/
Use `references/paperless-ngx-api.md` for a lightweight checklist and pointers to the official API documentation.
