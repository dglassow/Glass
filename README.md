# Glass

### Everything running on your computers, on every screen you own.

![The Glass app: a list of AI assistants, rooms, and live sessions across four computers, with one assistant's session open in the main pane](assets/glass.png)

Start something on your desktop. Close the lid. Open Glass on your phone an hour
later and it is still going, exactly where you left it.

Glass connects the computers you already own into one place you can reach from
anywhere. Your work keeps running on those machines whether or not the app is
open, whether or not your laptop is awake, and whether or not you are on the same
network. Nothing goes through anybody else's servers, because there aren't any.

### **[⬇ Download Glass 0.3.0 for Mac](../../releases/latest)**

For Apple Silicon Macs. Checked and approved by Apple. Drag it to Applications
and open it.

---

## What it's for

If you use more than one computer, work gets stranded. A long task is running on
the machine at home while you are out with the laptop. A file you need is on the
other desk. An AI assistant you set going has no idea what you asked the one on
your other machine.

Glass makes all of those computers act like one. You see everything that is
running, everywhere, from whichever screen is in front of you. You can pick up
any of it, hand work to any machine, and put your phone away without stopping it.

## Why people use it

**Your work does not stop when the app does.** The part of Glass that keeps your
work running is separate from the part you look at. Close the window, update the
app, let the laptop die: the work carries on untouched, and it is all still there
when you come back. Most tools lose everything at that moment. This one is built
so that it can't.

**Updates that cannot break you.** When Glass updates itself, it starts the new
version alongside the old one and checks that it genuinely works before retiring
anything. If the new version has a problem, the old one is simply still there.
You do not get a broken machine and a bad afternoon.

**Nobody in the middle.** Reaching your home computer from a coffee shop normally
means routing through some company's servers. Glass uses a cheap rented server
that acts as a dumb pipe and never holds the key to anything passing through it.
Even if someone took that server over completely, your devices would refuse to
talk to it. That is not a promise, it is something the software actively checks
every single time it connects.

**No passwords to steal.** Every device you add gets its own unforgeable
identity. Adding a new one is a six-digit code you confirm on a device you
already trust, the same way you pair headphones. There is no password anywhere
for someone to guess, phish, or leak.

**Built to be broken on purpose.** Before any version is released, 71 automated
tests try to destroy it: killing things mid-task, faking identities, corrupting
backups, impersonating the server in the middle. It only ships if it survives all
of them.

---

## What you can do with it

**See every machine at once.** Every computer you own, every session running on
it, live, from any of your devices. A colored dot tells you whether something is
working away or waiting on an answer from you.

**Put AI assistants to work and walk away.** Run several at the same time across
different machines. They keep working with the app closed. Everything that needs
your decision collects in one place instead of scattering across windows.

**Give the assistants a team.** Each one lives on a machine with its own job, its
own folder, its own memory and personality. Put a few in a room together and they
hand work to each other, but only with your say-so. Every decision you approve is
written down. You can also set them to start on a schedule.

**Let one drive the computer.** With your explicit permission, an assistant can
use a machine's mouse, keyboard, and screen while you watch it happen and take
over the moment you want to.

**Keep your passwords and keys safe.** A locked vault for the secrets your
machines need, opened by a passphrase with a printed recovery key as a backup.
One encrypted backup file holds everything, and restoring it onto a brand new
computer is a tested procedure rather than a hope.

**Browse from a different computer.** Read pages on the laptop in front of you
while they are actually fetched by the machine at home. Fast, because it is not
streaming video of a screen at you.

**Run your own private code storage.** Your own machine hosts your projects
privately for your other devices, with no third party involved.

**Carry it on your phone.** Glass installs on a phone like a normal app and gives
you a clean chat view for talking to your assistants from anywhere.

---

## Is Glass for you?

Honest answers, so you do not waste an afternoon.

**Glass is a good fit if** you own several computers, you already work in
technical tools day to day, and you want your own setup instead of a subscription
to somebody else's.

**Glass is not a good fit if** you want something that works the moment you sign
up. There is no signup. You run this yourself, and that means setting up one of
your machines as the hub the others connect through. That is deliberate. It is
also the reason nobody else can read your data.

**Right now it runs on Apple Silicon Macs.** Linux support is finished and tested
but has not been released. The phone version is chat only.

---

## Questions

**Do I need to be a programmer?** Realistically, yes. Glass is built for people
who work in a terminal and use AI coding assistants. It does not try to be a
general consumer app.

**Where does my data go?** Onto your own computers, and nowhere else. The rented
server in the middle only ever sees scrambled data it cannot unlock. Your
conversations and screens travel directly between your own devices.

**What does it cost?** Nothing. It is free for personal use. You pay only for the
cheap server in the middle if you want to reach your machines from outside your
home.

**Can I use my own AI tools?** Yes. Etch, Codex, and Claude work out of the box,
and other command-line assistants can be added.

**Is the code public?** No. Glass is private software. The app you download is
covered by the license in this repository.

---

## License

Glass is proprietary. [LICENSE](LICENSE) covers the app you download: install and
use it yourself, for personal and non-commercial purposes, and do not
redistribute, resell, modify, or take it apart.

This repository holds the downloads, the license, and the notices for other
people's software included in the app. The source code is developed privately.

Glass includes third-party components under their own licenses, reproduced in
full in [THIRD_PARTY_NOTICES.md](THIRD_PARTY_NOTICES.md).
