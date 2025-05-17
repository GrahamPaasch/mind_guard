# AGENTS.md

## Purpose
Provide context and rules for AI code generation. Loaded automatically by Codex to guide code, enforce conventions, and embed domain knowledge.

## Project Overview
MindGuard is a patient engagement tool for psychosis. It must deliver safe, benign interactive experiences (chatbot, simple games, cognitive exercises). Prevent unsafe behavior by keeping users engaged.

## Domain Constraints
- Do not expose or store protected health information (PHI).  
- Encrypt all sensitive data at rest and in transit.  
- Comply with HIPAA-level security: access controls, audit logging, anonymization.  
- Include rate limits and bot-behavior safeguards to prevent infinite loops or unmoderated interactions.

## Architecture Guidelines
- Backend: Python ≥3.8, Flask or FastAPI.  
- Frontend: React with TypeScript.  
- Database: PostgreSQL.  
- Authentication: OAuth 2.0 or JWT.  
- Deployment: Docker containers, Kubernetes helm charts.

## Code Standards
- Python: PEP8, type hints, black formatting.  
- JavaScript/TypeScript: ESLint (Airbnb), Prettier.  
- Write unit tests for every new function.  
- Use pytest for Python, Jest for JS/TS.  
- CI: GitHub Actions to run lint, tests, security scans.

## Repository Layout
- `/backend` — Flask/FastAPI service  
- `/frontend` — React app  
- `/shared` — shared types, utilities  
- `/tests` — integration and end-to-end tests  
- `Dockerfile`  
- `docker-compose.yml`

## Commit Messages
- Format: `<scope>(<area>): <short description>`  
- Include issue or ticket number when available.

## Safety & Monitoring
- Log user interactions with timestamps and anonymized IDs.  
- Implement circuit breakers to exit loops after X iterations.  
- Add health-check endpoints.

## Testing & Validation
- Mock user sessions for load tests.  
- Validate input on both client and server.  
- Simulate error conditions (network failures, database timeouts).

## Documentation
- Generate OpenAPI spec for backend.  
- Update README.md when adding features.  
- Maintain CHANGELOG.md using “Keep a Changelog” format.  
