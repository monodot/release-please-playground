# release-please-playground

This is a test repo for trying out release-please with a monorepo of three
components: `runner`, `frontend`, and `library`.

## Commit messages

Use Conventional Commits for every commit. release-please reads these messages
to decide the next version and to write the changelog.

Format: `<type>(<scope>): <description>`

- `<scope>` should be the component you are changing: `runner`, `frontend`, or `library`.
- Common types: `feat`, `fix`, `docs`, `chore`, `refactor`, `test`, `ci`.
- A `feat` triggers a minor bump. A `fix` triggers a patch bump. Add `!` for a breaking change, which triggers a major bump.

Examples:

- `feat(frontend): add a dark mode toggle`
- `fix(library): handle an empty name`
- `chore(runner): update the base image`
