# AI4Tech Platform

Internal platform for AI developer tooling: a FastAPI portal, a usage analytics
pipeline on AWS, and Terraform infrastructure.

## Conventions
- Python 3.12, managed with uv. Run `uv sync` before working.
- Lint and format with ruff: `uv run ruff check .` and `uv run ruff format .`
- Tests use pytest and live in `tests/`. Every new endpoint needs a test.
- Infrastructure is Terraform in `infra/`. Never hardcode account IDs, regions,
  or ARNs; use variables.
- Never commit secrets. Keep `.env` files out of git. Reference secrets through
  AWS Secrets Manager.
- Keep commits small, with imperative messages ("Add usage endpoint").

## Layout
- `portal/`: FastAPI service
- `infra/`: Terraform modules and environments
- `.claude/`: hooks, skills, and settings for Claude Code
- `.github/`: instructions for GitHub Copilot

## Working rules for Claude
- Read the matching skill in `.claude/skills/` before creating a new service.
- Ask before deleting files or changing infrastructure.
- Never run `terraform apply` or any AWS command that changes resources.
