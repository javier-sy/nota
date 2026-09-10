# Nota

Composition assistant for [MusaDSL](https://musadsl.yeste.studio), the Ruby language for
algorithmic sound and music composition.

Nota gives an AI coding assistant working knowledge of MusaDSL: what the framework can do,
how it is idiomatically written, and what has already been built with it. It ships skills
covering the whole creative process — understanding the framework, exploring ideas, writing
code that runs, analysing the result, and consolidating what worked into practices of your
own. Everything is backed by a semantic knowledge base: MusaDSL's documentation, its API
reference, the demo projects, and — locally and privately, only if you index them — your own
works.

**[nota.yeste.studio](https://nota.yeste.studio)** is the documentation:
[what it does](https://nota.yeste.studio/#about) ·
[the skills](https://nota.yeste.studio/#skills) ·
[requisites](https://nota.yeste.studio/#prerequisites) ·
[install](https://nota.yeste.studio/#install) ·
[troubleshooting](https://nota.yeste.studio/#troubleshooting)

## What this repository is

The home of Nota, independent of any one assistant:

- **Releases** — the knowledge base itself (`knowledge.db.gz`), rebuilt whenever the MusaDSL
  sources change. Every installation downloads it from here, on its own, on first use.
- **Issues** — where to report a problem or ask for something, whichever assistant you use.

The plugin is installed through each assistant's own channel, not from here:
see [install](https://nota.yeste.studio/#install).

## License

The knowledge base released here is derived from MusaDSL's own documentation,
source and demo projects, and is distributed under the same terms as MusaDSL:
**LGPL-3.0-or-later**.

The Nota plugin is a separate work with a separate license. It is free of charge
and proprietary: it is licensed to be used, not copied, changed or
redistributed, and what you compose with it is yours without condition. Its
terms travel with it, in the `LICENSE` file of the installed plugin.

Copyright © Javier Sánchez Yeste, [yeste.studio](https://yeste.studio).
