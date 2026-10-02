# catalog-kotlin-ktor-template

A minimal, idiomatic **Kotlin + Ktor** starter used as the shared scaffold for DayZer0's
Kotlin + Ktor catalog briefs. Every board in that bucket is provisioned from this repository,
so you clone it, run it, and build the brief's features on top of it — you do **not** create
the project from scratch.

## What's here

- A Ktor server on **Netty** (`src/main/kotlin/com/dayzer0/app/Application.kt`).
- **ContentNegotiation** installed with **kotlinx.serialization** JSON, so routes speak JSON.
- `GET /healthz` returning `{"status":"ok"}` — the health route the setup ticket asks you to confirm.
- A `testApplication` test proving `/healthz` answers `200` (`src/test/kotlin/...`).
- The Gradle build (`build.gradle.kts`) with Ktor, Netty, ContentNegotiation and serialization pinned.

## Requirements

- A JDK, **17 or newer** (the Gradle toolchain targets 17).

## Run it

```bash
./gradlew run
```

Then, in another terminal:

```bash
curl http://localhost:8080/healthz
# {"status":"ok"}
```

## Test it

```bash
./gradlew test
```

## Where your work goes

- Routes: add them in `Application.module()` (or split into route files it calls).
- Models: `@Serializable` data classes; they serialise through the ContentNegotiation already installed.
- Keep business logic in plain functions and classes, not inside route handlers, so it is unit-testable without HTTP.

## Submitting work

One ticket, one branch, one pull request. Put `Closes #N` in the PR body (see
`.github/PULL_REQUEST_TEMPLATE.md`) so the merge submits the ticket. Never commit on `main`.
