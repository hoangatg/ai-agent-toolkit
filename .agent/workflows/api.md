---
description: API design workflow. Design, document, and generate API endpoints with OpenAPI specifications.
---

# /api - API Design

$ARGUMENTS

---

## Task

Design and document a clean, consistent API.

### Steps:

1. **Requirements**
   - Define resources and relationships
   - Determine API style (REST, GraphQL, tRPC)

2. **Design**
   - Use `api-designer` agent for schema design
   - Define endpoints, methods, request/response shapes
   - Plan authentication and authorization

3. **Documentation**
   - Generate OpenAPI/Swagger specification
   - Create example requests and responses

4. **Implementation**
   - Use `backend-specialist` agent to implement
   - Set up validation with Zod/Pydantic

5. **Testing**
   - Generate API test suite
   - Verify with integration tests

---

## Usage Examples

```
/api users                 # Design users API
/api graphql schema        # Design GraphQL schema
/api rest --resource posts # Design REST posts endpoints
```
