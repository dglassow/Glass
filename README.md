# Glass

### Your machines. Your agents. One app that never loses your place.

![The Glass desktop app: a sidebar of bots, rooms, and live terminals across four machines, with an AI agent session open in the main pane](assets/glass.png)

Close the lid. Get on a plane. Open Glass on your phone. The build is still
running, the agent is still working, and every line of scrollback is exactly
where you left it.

Glass is a self-hosted client for terminal sessions and AI coding agents across
your own computers. Sessions live in a daemon that outlives the app, so updates,
restarts, crashes, and dead Wi-Fi never touch them. No company sits between you
and your machines. No account. No cloud.

### **[⬇ Download Glass 0.3.0 for macOS](../../releases/latest)**

Apple Silicon. Signed with a Developer ID and notarized by Apple. Drag to
Applications and launch.

---

## The problem

SSH drops the moment your laptop sleeps. `tmux` keeps a session alive on exactly
one box and offers nothing on a phone. Your AI agents each run in their own
silo, on one machine, blind to each other. And updating any of it kills whatever
was running.

Every one of those is a consequence of treating the session as disposable.

## The fix

Glass treats the session as the thing worth protecting, and builds everything
else around that.

**Terminals that outlive the software running them.** PTY file descriptors live
in a daemon separate from the app. The process that routes your traffic gets
swapped blue/green: the replacement has to pass a health check before the old one
retires, and a failure rolls back instantly. Your shell never notices. Neither
does the agent working inside it.

**A relay that physically cannot read your traffic.** Reaching your machines from
anywhere usually means trusting a middleman. Glass uses a bare VPS running
nothing but stock `sshd`. Your hub dials out and holds a reverse tunnel, TLS
terminates inside your hub instead of at the relay, and clients pin the hub's
identity bound to the TLS exporter. A man-in-the-middle holding a perfectly valid
certificate still gets refused. There is a test that stands up a real hostile
relay to prove it.

**Keys, not passwords.** Every device carries an Ed25519 key and proves it by
challenge and response. Adding a machine is a six-digit number match between the
joiner and an approver, like pairing headphones. The first device on a fresh
install bootstraps from a WebAuthn passkey, so there is no chicken and egg.

**An updater built like it is under attack.** Backend services update only from
SSH-signed git tags, verified against a key pinned outside the repository being
checked. The fetched repository is treated as hostile throughout: tags resolve to
an immutable object once and that same object is used for both verification and
extraction, extraction refuses symlinks and submodules, and every git call runs
hardened. That last measure closed a real remote-code-execution path found during
red teaming.

**Proof, not promises.** Every release is gated on 71 adversarial test harnesses.
They are not mocks. They start real daemons, real TLS listeners, real git servers
and real terminals, then kill things at the worst possible moment and assert the
system survives.

---

## What you can do with it

**Run terminals across every machine you own.** Every device sees every machine's
sessions live. Status dots tell you at a glance whether the agent in each
terminal is idle, working, or waiting on you.

**Run AI agents that outlive their window.** Etch, Codex, Claude, and any
command-line agent you configure, working at the same time across machines, with
one inbox for everything that needs your attention. Runs live in the daemon.
Close the app, replace the worker, and they keep going.

**Give the agents a team.** Durable bots that live on a device, each with its own
engine, working folder, persona, editable memory, and optional real terminal. Put
several in a room with you and they delegate to each other, one hop deep, behind
a peer-approval gate. Every consent decision lands in a log. Routines start fresh
threads on a schedule.

**Hand a bot the actual computer.** Mouse, keyboard, and screen, under an explicit
approval scope, with a single-holder lease, live preview, and instant human
takeover.

**Keep secrets properly.** Envelope encryption over SQLite, a passphrase and an
offline recovery key in independent keyslots, per-device scoping, and injection
into a child process environment only. One encrypted bundle backs up secrets,
trust, tokens, and every hosted git repository, and it passes a wipe-and-restore
drill onto clean hardware.

**Browse from somewhere else.** Put a SOCKS exit on one machine and an isolated
browser profile on another. Render locally, egress from the machine you choose.
No pixel streaming, no lag.

**Host your own git.** Your hub serves bare repositories to your devices over
authenticated smart-HTTP on its existing TLS listener, with per-device tokens and
per-repository access control.

**Carry it in your pocket.** The same frontend, served by your hub as an
installable web app, with a focused surface for talking to your agents from
anywhere.

---

## How it works

One codebase, three roles. Any supported desktop can be a **Hub** (registry,
auth, vault, relay, updates, git hosting) or an **Agent** (hosts sessions), and
every device is a **Viewer**.

Four processes per machine: a supervisor that owns lifecycle and depends on
nothing, a session daemon that owns terminals and agent runs and survives
updates, a bot daemon, and a swappable worker. Every message on the wire carries
its protocol version, so a hub mid-rollout can hold connections from devices on
two versions at once.

---

## Scope

- **macOS on Apple Silicon.** Debian 13 support is built and verified on native
  amd64 and arm64 continuous integration, but no Debian artifact has shipped yet.
- **Mobile is a web app, chat only.** Terminals, browser proxying, and computer
  control are native features by design.
- **You run the infrastructure.** Glass is personal infrastructure, not a hosted
  product. Using it means running your own hub and enrolling your own devices.
  That is the point: there is no server of ours holding anything of yours.

---

## Questions

**Is this just a terminal emulator?** It has one, but the value is the session
layer beneath it: terminals that live in a daemon, reachable from every device
you own, that survive the app being updated or replaced.

**How is it different from `tmux` over SSH?** `tmux` pins a session to one host.
It gives you nothing on a phone, no cryptographic device identity, no fleet-wide
view, and no way to update itself without killing your work. Glass is built
around those four gaps.

**Does my data pass through anyone's servers?** No. The relay is a VPS you
provision that runs only stock `sshd` and never sees plaintext. Thread content
and screen frames travel point to point between your own devices, and the hub
persists only content-free records.

**Can I bring my own AI agents?** Yes. Etch, Codex, and Claude are supported
directly, and any other command-line agent can be configured as a generic
provider.

**Is it open source?** No. Glass is proprietary and the source is private. The
published binaries are covered by the license here.

---

## License

Glass is proprietary. [LICENSE](LICENSE) covers the published binaries: install
and run it for personal, non-commercial use, and do not redistribute, resell,
modify, or reverse engineer it.

This repository holds the release artifacts, the license, and the third-party
notices. The source is developed privately. Tags here exist only to anchor
releases; they are not source revisions and are not signed source tags.

Glass includes third-party components under their own licenses, reproduced in
full in [THIRD_PARTY_NOTICES.md](THIRD_PARTY_NOTICES.md). Those terms govern
those components and are not limited by the Glass license.
