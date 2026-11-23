<p align="center"><img src="docs/images/alondra1-logo-512.png" alt="Alondra1 logo" width="128"></p>

# Alondra1 for Mac

[![ci](https://github.com/nikita4sea/alondra1-mac/actions/workflows/ci.yml/badge.svg)](https://github.com/nikita4sea/alondra1-mac/actions/workflows/ci.yml)

Planned macOS client. **Nothing is implemented yet, and the [backend specification](https://github.com/nikita4sea/alondra1-backend/blob/main/docs/BACKEND_SPEC.md) does not define a macOS scope yet.** Until it does, the cross-client rules below apply, and the Windows app ([alondra1-windows](https://github.com/nikita4sea/alondra1-windows)) is the reference for desktop behavior.

## Scope

Not defined yet. Decide it (and record it as a decision in alondra1-backend) before starting: whether the Mac app is a tasks-and-settings client like Android and iOS, or a full desktop client with mail, calendar, and organizer like Windows.

Details: [docs/CLIENT-REQUIREMENTS.md](docs/CLIENT-REQUIREMENTS.md).

## Getting started

When the project is created, put the Xcode project or Swift package at the repository root here. Expected commands:

```sh
xcodebuild test -scheme Alondra1 -destination 'platform=macOS'
```

Cloud settings for development (API base URL and so on) go in a local `.env` copied from [.env.example](.env.example); never commit it or any credentials.

## CI

The [`ci`](.github/workflows/ci.yml) workflow checks Markdown links and scans for secrets on every push and pull request. Its build job starts automatically once the project files exist (it is skipped until then).

## Related repositories

[alondra1-backend](https://github.com/nikita4sea/alondra1-backend) (cloud API and contract) · [alondra1-windows](https://github.com/nikita4sea/alondra1-windows) (reference client) · [alondra1-www](https://github.com/nikita4sea/alondra1-www)

## License

[MIT](LICENSE)
