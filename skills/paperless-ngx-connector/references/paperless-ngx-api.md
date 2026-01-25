# Paperless-ngx API Notes

Use this file as a lightweight checklist and pointer to the official API docs:
https://docs.paperless-ngx.com/api/

## Required inputs

- Base URL for the Paperless-ngx instance
- API token for a user account
- TLS settings (verify or custom CA) if needed

## Authentication

- Confirm the exact auth header format in the official docs before making calls.
- If authentication fails, verify the token and instance URL.

## Common tasks

- List/search documents
- Upload a document and set metadata
- Update tags, correspondent, document type, storage path
- List metadata entities (tags, correspondents, document types, storage paths)

## Suggested verification flow

1. Call a simple GET endpoint (e.g., list documents) to verify connectivity.
2. Perform the requested operation.
3. Re-fetch the object to confirm the update or upload succeeded.

## Safety and handling

- Do not log tokens or secrets.
- Surface HTTP status codes and validation errors to the user.
