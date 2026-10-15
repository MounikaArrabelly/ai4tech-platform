name: python-service
description: Use when creating or modifying a Python FastAPI service, router, or endpoint in this repo.
---

# Python service conventions

1. Layout: routers go in `portal/routers/`, pydantic models in `portal/schemas.py`,
   business logic in `portal/services/`. Routers stay thin.
2. Every endpoint has a test in `tests/` using FastAPI's `TestClient`.
3. Status codes: 404 for missing resources, 403 for access denied, 422 for invalid
   input (pydantic returns this automatically).
4. Log with the `logging` module. No `print` statements.
5. A change is done when `uv run ruff check .` and `uv run pytest` both pass.