# Contributing to Ludexis

Thanks for helping out. Ludexis is split into three repositories; open issues and pull requests where the change lives:

| Change | Repository |
| ------ | ---------- |
| API, scanner, metadata, jobs, database | [ludexis-backend](https://github.com/Ludexis/ludexis-backend) |
| Web app, pages, components | [ludexis-frontend](https://github.com/Ludexis/ludexis-frontend) |
| Docker Compose, deployment, documentation | [Ludexis](https://github.com/InvictusRex/Ludexis) |

## Setting up

Clone everything at once and start PostgreSQL and Redis:

```bash
git clone --recurse-submodules https://github.com/InvictusRex/Ludexis.git
cd Ludexis
docker compose -f docker-compose.dev.yml up -d
```

`backend/` and `frontend/` are the two repositories, checked out as submodules. Each README explains how to run that part. To work on one of them alone, clone it directly.

## Reporting a bug

Include what you did, what you expected, what happened instead, your Ludexis version (image tag) and the relevant logs (`docker compose logs backend worker`). Leave out passwords, API keys and private paths.

## Pull requests

1. Fork the repository and branch from `main`.
2. Keep the change focused: one fix or feature per pull request.
3. Add or update tests for what you change.
4. Run the checks before pushing:
   - backend: `pytest`
   - frontend: `npm run lint`, `npx tsc --noEmit`, `npm test`
5. Write commit messages as [Conventional Commits](https://www.conventionalcommits.org/): `type(scope): description`, for example `fix(scanner): skip unreadable folders`.
6. Describe what changed and why in the pull request, with screenshots for visible changes.

CI runs the same checks on every pull request. Database changes need an Alembic migration (`alembic revision --autogenerate -m "..."`).

## Code style

Follow the style of the surrounding code. Backend: typed Python, business logic in `app/services`, queries in `app/repositories`. Frontend: TypeScript, Tailwind, shared primitives from `components/ui`.

## License

By contributing you agree that your contributions are released under the MIT License.
