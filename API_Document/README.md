# CAB System API Documentation

## Files

- `openapi.yaml`: Entry point for the modular documentation. It references the path and component files.
- `paths/`: Endpoint definitions grouped by business module.
- `components/`: Shared schemas, responses and security definitions.
- `swagger.yaml`: Bundled, standalone OpenAPI document for Swagger Editor, Swagger UI or SwaggerHub.

## Swagger

Upload `swagger.yaml` to Swagger Editor or import it into SwaggerHub. It contains no external file references.

## Rebuild the bundle

From the repository root:

```powershell
npx --yes @redocly/cli bundle API_Document/openapi.yaml -o API_Document/swagger.yaml
npx --yes @redocly/cli lint API_Document/swagger.yaml
```

The production and local server URLs in `openapi.yaml` are placeholders and should be replaced when the environments are available.
