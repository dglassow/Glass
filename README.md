# Glass

A unified client for running terminal sessions across your own machines, with a
chat surface for mobile.

One app, three roles. Any supported desktop can be a **Hub** (registry, auth,
vault, relay, update distribution, git hosting) or an **Agent** (hosts
sessions), and every device is a **Viewer** — a native app on macOS and Debian
13, or a chat-only PWA elsewhere.

## Download

Signed and notarized macOS builds are published on the
[Releases](../../releases) page. Download the `.dmg`, open it, and drag Glass to
Applications. Once installed, updates are delivered in-app.

Glass is built as personal infrastructure for its author's own fleet. Running it
means standing up your own hub and enrolling your own devices; there is no
hosted service to sign up for.

## Source

This repository holds the release artifacts, the license, and the third-party
notices. The source code is not public and is developed in a private
repository.

Tags in this repository exist only to anchor releases. They do not correspond to
source revisions and are not signed source tags.

## License

Glass is proprietary. See [LICENSE](LICENSE) for the terms that apply to the
published binaries. In short: install and run it for personal, non-commercial
use; do not redistribute, resell, modify, or reverse engineer it.

Glass includes third-party components under their own licenses, reproduced in
[THIRD_PARTY_NOTICES.md](THIRD_PARTY_NOTICES.md). Those terms govern those
components and are not limited by the Glass license.
