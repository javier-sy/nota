# Nota

Composition assistant for [MusaDSL](https://musadsl.yeste.studio), the Ruby language for
algorithmic sound and music composition.

Nota gives an AI coding assistant working knowledge of MusaDSL: what the framework can do,
how it is idiomatically written, and what has already been built with it. It ships skills
covering the whole creative process — understanding the framework, exploring ideas, writing
code that runs, analysing the result, and consolidating what worked into practices of your
own.

Everything is backed by a semantic knowledge base: MusaDSL's documentation, its API
reference, the demo projects, and — locally and privately, only if you index them — your own
works.

**Website:** [nota.yeste.studio](https://nota.yeste.studio)

## What this repository is

The home of Nota, independent of any one assistant:

- **Releases** — the knowledge base itself (`knowledge.db.gz`), rebuilt whenever the MusaDSL
  sources change. Every installation downloads it from here, on its own, on first use.
- **Issues** — where to report a problem or ask for something, whichever assistant you use.

The plugin is installed through each assistant's own channel, not from here.

## Install

### Claude Code

```
/plugin marketplace add javier-sy/claude-plugins
/plugin install nota@yeste.studio
/nota:setup
```

Then leave with `/exit` and come back with `claude --continue`: that returns to the same
conversation and starts the knowledge base, so its tools become available.

### opencode

On hold. [nota.yeste.studio](https://nota.yeste.studio) says when it returns.

## What it needs

Nota asks for four things. **`/nota:setup` checks all four and names the one that is
missing**, so this list is where to look when it does.

- **Ruby 3.1 or later**, built for the architecture you are running on.
- **A Voyage AI API key**, for the embeddings — one comes from
  [dash.voyageai.com](https://dash.voyageai.com/).
- **`sqlite3` and `sqlite-vec` available for that Ruby.** This is the one real constraint,
  and it comes from upstream rather than from Nota: `sqlite-vec` publishes a Windows build
  for x64 and none for ARM, so a Ruby reporting `aarch64-mingw-ucrt` cannot open the
  knowledge base. Windows on ARM runs an x64 Ruby under emulation — rather than putting it
  first on `PATH`, point Nota at it:

  ```powershell
  [Environment]::SetEnvironmentVariable('NOTA_RUBY', 'C:\Ruby34-x64\bin\ruby.exe', 'User')
  ```

- **Network access, once**: installing the plugin downloads nothing. `/nota:setup` fetches
  the dependencies, the extension and the index, and after that Nota works offline except
  for the embeddings.

## What lands on your machine

Everything goes to `~/.config/nota/`, outside the plugin directory, so it survives updates:
the Ruby dependencies, the `sqlite-vec` extension, and the knowledge base from this
repository's latest release.

Your own indexed works live beside them in `private.db`, which is created empty the first
time you index something and is never touched by an update. Nothing from it leaves your
machine.

## Licence

GPL-3.0-or-later. Copyright © Javier Sánchez Yeste, [yeste.studio](https://yeste.studio).
