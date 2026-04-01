# Copilot Instructions: Mergington High School Activities API

## Project Description

This project is a small educational web application for managing extracurricular
activities at Mergington High School.

- Backend: exposes API endpoints to list activities and sign students up.
- Frontend: simple static UI served by the backend.
- Data: stored in memory for learning purposes (no database persistence).

## Technology Stack

- Python 3
- FastAPI
- Uvicorn (local development server)
- Static frontend assets (HTML, CSS, JavaScript) in `src/static/`
- Pytest configuration in `pytest.ini`

## Architecture Notes

- Main application entry point: `src/app.py`
- Static files are mounted under `/static`
- Root route (`/`) redirects to the static frontend
- Activity data currently lives in an in-memory dictionary called `activities`

## Coding Guidelines

1. Keep changes small, focused, and easy to review.
2. Prefer clear and explicit code over clever shortcuts.
3. Preserve existing API behavior unless a task explicitly requires a breaking
   change.
4. Add input validation for new user inputs and return appropriate HTTP errors.
5. Use FastAPI conventions for routing, typing, and response handling.
6. Keep business logic separate from route wiring when complexity grows.
7. For new features, update or add tests where practical.
8. Do not introduce new dependencies unless they are necessary.
9. Keep comments concise and only where they add real clarity.
10. Follow existing naming and formatting patterns in the repository.

## API Guidelines

- Keep route naming consistent with existing endpoints.
- Return structured, predictable JSON responses.
- Use meaningful HTTP status codes:
  - `200` for successful reads
  - `201` for successful creations (if introduced)
  - `400` for invalid input
  - `404` for missing resources
  - `409` for conflicts (for example, duplicate signups)

## Frontend Guidelines

- Keep static assets lightweight and framework-free unless requested otherwise.
- Prefer accessible markup and clear form validation messages.
- Keep UI behavior consistent with backend validation and response messages.

## Non-Goals (Current Scope)

- No database or external persistence yet.
- No authentication or authorization yet.
- No background jobs or message queues.

## When Extending This Project

- If adding persistence, introduce a clear data access layer instead of mixing
  storage logic directly into route handlers.
- If adding auth, keep public and protected endpoints explicitly separated.
- If the API grows, consider versioning routes (for example, `/api/v1/...`).