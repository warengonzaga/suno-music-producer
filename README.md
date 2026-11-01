# Suno Music Producer

![Suno Music Producer banner — Faithful Suno production, guided by your workflow](https://ghrb.waren.build/render/banner?header=Suno+Music+Producer&subheader=Faithful+Suno+production%2C+guided+by+your+workflow&bg=090D24-33225F&color=FFFFFF&subheadercolor=D9E8FF&headerfont=Inter&subheaderfont=Inter&support=true&stats=false)
<!-- Created with GitHub Repo Banner by Waren Gonzaga: https://ghrb.waren.build -->

Suno Music Producer is a Codex plugin that helps people write original lyrics, create songs, and reimagine music through Suno. It bundles the Suno MCP connection with a reusable skill that learns preferences from each user's request, project, and feedback instead of imposing one artist's preset.

## ✨ Features

- Bundles Suno's remote MCP endpoint at https://api.suno.com/mcp with the production skill.
- Helps write original songs, from concept and story through hooks, complete lyrics, and revisions, using each songwriter's preferred process.
- Builds Style prompts and handles exclusions in the format each user prefers and Suno supports.
- Creates song-specific lyrics section directions, from concise guidance to detailed vocals, instruments, energy, effects, and restrictions.
- For covers, preserves the approved lyrics, melody, composition, arrangement, sections, BPM, key, and ad-libs unless you request changes.
- Checks existing source clips and workspaces, discovers the project's model and voice preferences, verifies current Suno options, and checks the complete brief before spending generation credits.
- Includes Supernova (Reimagined) as one project-specific example at 120 BPM in Bb major; those settings are not global defaults.

## 🚀 Getting Started

### Requirements

- Codex with plugin marketplace support.
- Access to Suno MCP and authorization if prompted by Codex. MCP access may be limited or invite-only.

> **Suno MCP access:** Suno controls access to its MCP service, and it may not be available to every user. Installing this plugin does not grant or guarantee access. Without Suno MCP access, the skill can still help prepare original lyrics, prompts, and production instructions, but it cannot generate songs through Suno.

### Install

The plugin is available from the stable `main` branch. Add the repository as a marketplace:

    codex plugin marketplace add warengonzaga/suno-music-producer

Open Codex's **Plugins Directory**, select the Suno Music Producer marketplace, and install the plugin. Start a new chat to use the skill and complete Suno authorization if prompted. To refresh it after an update, run `codex plugin marketplace upgrade suno-music-producer`.

### First production request

Ask Codex to use Suno Music Producer to write an original song, produce an existing lyric draft, or prepare a cover. Describe your goals and any preferences you already have; for a cover, identify the source track and what should be preserved. The skill will use available project context to shape a workflow for you and flag only choices that need your input.

## 📖 Usage

Example request:

    Use Suno Music Producer to help me write an original song from this idea: [your idea]. Discover my preferred collaboration process, develop original lyrics, check singability, and prepare the Suno materials. Keep my approved preferences for this project.

The skill discovers your preferred Style and exclusions format, prepares complete lyrics with project-specific section directions, and recommends supported controls. It verifies a generated clip's status and reports a song link only when Suno returns one and the result is playable.

See the [Supernova production example](plugins/suno-music-producer/skills/suno-music-producer/references/supernova-example.md) for one user's format; its settings are example-specific, not defaults.

## 📚 Documentation

- [Suno Music Producer skill](plugins/suno-music-producer/skills/suno-music-producer/SKILL.md) — workflow, cover preservation, prompt construction, preflight, and result verification.
- [Story-driven songwriting workflow](plugins/suno-music-producer/skills/suno-music-producer/references/story-driven-songwriting.md) — one optional section-by-section writing method; the skill follows each songwriter's preferred process.
- [Supernova (Reimagined) reference](plugins/suno-music-producer/skills/suno-music-producer/references/supernova-example.md) — an example combined Style prompt and full section-by-section lyrics for one specific project.
- [Codex plugin marketplace documentation](https://developers.openai.com/plugins/build/plugins) — adding a repository marketplace and installing a plugin.
- [Clean README specification](https://github.com/wgtechlabs/clean-readme/blob/main/SPECIFICATION.md) — README structure and conformance guidance.

## 🛠️ Development

This repository packages plugin manifests, an MCP connection, and skill documentation. It does not currently define a build or automated test script.

Validate the JSON manifests with Python:

    python -m json.tool .agents/plugins/marketplace.json
    python -m json.tool plugins/suno-music-producer/plugin.json
    python -m json.tool plugins/suno-music-producer/mcp.json

These checks confirm JSON syntax only. They do not install the plugin, authenticate with Suno, or verify a live generation.

## 🤝 Contributing

Contributions are welcome. Create a short-lived feature branch from dev and target pull requests to dev. Use the repository's Clean Commit format, and follow the review and release workflow in the repository instructions.

## 🐛 Issues & Support

Report bugs, request changes, and ask project questions in the [GitHub issue tracker](https://github.com/warengonzaga/suno-music-producer/issues). Include the relevant plugin version and steps to reproduce an issue. Do not post Suno credentials, tokens, or private account information.

## 📄 License

No license has been specified for this repository yet.

## 👥 Authors & Contributors

Created by [Waren Gonzaga](https://github.com/warengonzaga). See the [contributors page](https://github.com/warengonzaga/suno-music-producer/graphs/contributors) for repository contributors.
