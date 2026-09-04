# Glass

**Your terminals, your machines, your AI agents. One app, everywhere, and the sessions never die.**

Glass is a self-hosted client for running terminal sessions and AI coding agents
across your own computers. Open a shell on your Mac Studio from your laptop.
Leave it running. Update the app, restart the machine's backend, walk away for a
week, then pick the same shell up from your phone with the scrollback intact.

It is a native macOS application plus an installable chat app for mobile, backed
by infrastructure you run yourself. There is no company between you and your
machines, no hosted service, and no account to create.

---

## Download

**[Download Glass 0.3.0 for macOS](../../releases/latest)** — Apple Silicon, signed
with a Developer ID and notarized by Apple.

Open the disk image, drag Glass to Applications, and launch it. Later updates
arrive inside the app.

---

## Why Glass exists

Remote terminal work is held together by tools that were never designed for it.
SSH drops when your laptop sleeps. `tmux` and `screen` keep sessions alive but
die with the machine's uptime and give you nothing on a phone. Every AI coding
agent runs in its own silo, on one machine, with no memory of the others.
Updating any of it kills whatever was running.

Glass treats the session as the thing worth protecting, and builds everything
else around that decision.

---

## What makes it different

**Terminal sessions survive routine updates.** This is the load-bearing design
decision. PTY file descriptors live in a dedicated daemon that outlives the
application. The worker process that routes traffic is swapped blue/green, health
checked before the old one retires, and rolled back instantly if the new one
fails to come up. Your shell does not notice. Neither does the AI agent running
inside it.

**A relay that cannot read your traffic.** Reaching your machines from anywhere
normally means trusting a middleman. Glass runs a dumb VPS with nothing on it but
stock `sshd`. Your hub dials out and holds a reverse tunnel, TLS terminates
inside your hub rather than at the relay, and clients pin the hub's identity key
bound to the TLS exporter. A man-in-the-middle that terminates TLS is refused
even when it presents a perfectly valid certificate. That case is covered by a
test that stands up a real hostile relay and proves the connection fails.

**Real cryptographic identity, not passwords.** Every device holds an Ed25519
key and proves possession through challenge and response. Adding a device is a
six-digit number match between the joiner and an approver, the same ritual as
pairing headphones, and the first device on a fresh install bootstraps from a
WebAuthn passkey so there is no chicken-and-egg problem.

**An updater built like it is under attack, because it is.** Backend services
update only from SSH-signed git tags, verified against a key pinned outside the
repository being verified. The fetched repository is treated as hostile input
throughout: a tag is resolved to an immutable object once and that same object is
used for both verification and extraction, extraction refuses symlinks and
submodules, and every git invocation runs under a hardened configuration. That
last measure closed a real remote-code-execution path found during red teaming.

**Verification that spawns real processes.** Every release is gated on 71
adversarial test harnesses. They are not mocks. They start real daemons, real TLS listeners,
real git servers, real PTYs, then kill things at the worst possible moment and
assert the system survives. Restart resilience, cross-device isolation, spoofed
frames, tampered backups, hostile relays, and rollback are all regression-covered.

---

## Features

**Terminals across your fleet.** Every viewer sees every machine's sessions live.
Status dots show whether the agent in each terminal is idle, working, or waiting
on you. Rename, reattach, and pick up any session from any device.

**AI agents that outlive their window.** Run Etch, Codex, Claude, and configured
generic CLI agents concurrently across machines, with one attention inbox for
everything that needs you. Runs live in the daemon, so closing the app or
replacing the worker leaves them working. Approvals, clarifications, streaming
output, attachments, and provider-native resume all ride the same interface.

**Bots, threads, and rooms.** Durable AI teammates that live on a device, each
with its own engine, working folder, persona, editable memory, and optional real
terminal. Put several in a room with you, and they delegate to each other one hop
deep behind a peer-approval gate. Every consent decision lands in a per-device
log. Scheduled routines start fresh threads on their own.

**Host computer control.** A bot can drive a device's mouse, keyboard, and screen
under an explicit approval scope, with a single-holder lease, live preview, and
immediate human takeover.

**An encrypted vault.** Envelope encryption over SQLite with a passphrase and an
offline recovery key in independent keyslots, per-device secret scoping, and
injection into a child process's environment only, with structural redaction in
logs. One encrypted bundle backs up secrets, trust, tokens, and every hosted git
repository, and it passes a wipe-and-restore drill onto clean hardware.

**Cross-device browsing.** Put a SOCKS exit on one machine and an isolated
browser profile on another: render locally, egress from the machine you choose.
No pixel streaming, no lag.

**Git hosting.** Your hub serves bare repositories to your devices over
authenticated smart-HTTP on its existing TLS listener, with per-device tokens and
per-repository access control. Repositories ride the backup bundle.

**A chat app for your phone.** The same frontend, served by your hub as an
installable progressive web app, with a focused conversation surface for talking
to your agents from anywhere.

---

## How it works

One codebase, three roles. Any supported desktop can be a **Hub** (registry,
authentication, vault, relay, update distribution, git hosting) or an **Agent**
(hosts sessions), and every device is a **Viewer**.

Under the hood, four processes per machine: a protocol-free supervisor that owns
lifecycle, a session daemon that owns PTYs and agent runs and survives updates, a
bot daemon, and a swappable worker. Every message on the wire carries its
protocol version, so a hub mid-rollout can hold connections from devices on two
versions at once.

---

## Requirements and scope

- **macOS on Apple Silicon** for the released application. Debian 13 support is
  built and verified on native amd64 and arm64 continuous integration, but no
  Debian artifact has been released yet.
- **Mobile is a progressive web app**, chat only. Terminal panes, browser
  proxying, and computer control are native features by design.
- **You run the infrastructure.** Glass is personal infrastructure rather than a
  hosted product. Using it means running your own hub and enrolling your own
  devices. There is no signup, and there is no server of ours holding your data.

---

## Source and license

This repository holds the release artifacts, the license, and the third-party
notices. The source code is not public and is developed privately. Tags here
exist only to anchor releases; they do not correspond to source revisions and are
not signed source tags.

Glass is proprietary. See [LICENSE](LICENSE) for the terms covering the published
binaries: install and run it for personal, non-commercial use, and do not
redistribute, resell, modify, or reverse engineer it.

Glass includes third-party components under their own licenses, reproduced in
[THIRD_PARTY_NOTICES.md](THIRD_PARTY_NOTICES.md). Those terms govern those
components and are not limited by the Glass license.

---

## Questions

**Is Glass a terminal emulator?** It includes one, but the point is the session
layer underneath: sessions that live in a daemon, reachable from every device you
own, that survive the app being updated or replaced.

**How is this different from `tmux` over SSH?** `tmux` keeps a session alive on
one host and gives you nothing on a phone, no cryptographic device identity, no
fleet-wide view, and no story for updating itself without killing your work.
Glass is built around those gaps.

**Does my data pass through anyone's servers?** No. The relay is a VPS you
provision that runs only stock `sshd` and never sees plaintext. Thread content
and screen frames travel point-to-point between your own devices; the hub
persists only content-free records.

**Can I use my own AI agents?** Yes. Etch, Codex, and Claude are supported
directly, and any other command-line agent can be configured as a generic
provider.

**Is it open source?** No. Glass is proprietary and the source is private. The
published binaries are covered by the license in this repository.
