# Update and maintenance policy

`image_compression` is currently a minimal project placeholder. As implementation is added, use GitHub `main` as the single source of truth.

## Manual update

For a working checkout:

```bash
git fetch origin main
git switch main
git pull --ff-only origin main
```

Do not pull automatic updates from feature or development branches.

## Automatic updates

A self-updater is not added yet because this repository does not currently contain a runnable application or reusable runtime tool. If the project becomes an installable application, its updater must fetch only `origin/main`, refuse local changes or diverged history, synchronize dependencies from the declared manifest/lock file, validate the updated build, and preserve a known-good revision for recovery.

## Dependency policy

When dependencies are introduced, they must be declared in the appropriate manifest and lock file where the ecosystem supports one. Do not introduce packages that are explicitly deprecated or unmaintained when a supported replacement is available. Dependency changes should be validated by the project's build, tests, or linting before release.

## Releases

Use semantic versioning once the project has a runnable release artifact. Until then, documentation-only maintenance changes do not require a release tag.
