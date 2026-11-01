# Suno Music Producer

![Suno Music Producer banner — Faithful Suno production, guided by your workflow](https://ghrb.waren.build/render/banner?header=Suno+Music+Producer&subheader=Faithful+Suno+production%2C+guided+by+your+workflow&bg=090D24-33225F&color=FFFFFF&subheadercolor=D9E8FF&headerfont=Inter&subheaderfont=Inter&support=true&stats=false)
<!-- Created with GitHub Repo Banner by Waren Gonzaga: https://ghrb.waren.build -->

Suno Music Producer is a Codex plugin for creating and reimagining songs through Suno. It bundles the Suno MCP connection with a reusable skill that follows your production workflow for source checks, cover preparation, and generation.

## ✨ Features

- Bundles Suno's remote MCP endpoint at https://api.suno.com/mcp with the production skill.
- Builds one comma-separated Style prompt with positive instructions and dash-prefixed exclusions, within Suno's 1,000-character limit.
- Adds song-specific production directions to each bracketed lyrics section, including vocals, instruments, energy, effects, and restrictions.
- For covers, preserves the approved lyrics, melody, composition, arrangement, sections, BPM, key, and ad-libs unless you request changes.
- Checks the existing source clip and workspace, explicitly selects Suno v6, verifies the applicable artist voice (including Stella Pinoy Pop for Siren of the Stars), checks supported controls, and reviews the full prompt before spending generation credits.
- Includes the Supernova (Reimagined) example at 120 BPM in Bb major.

## 🚀 Getting Started

### Requirements

- Codex with plugin marketplace support.
- A Suno account and authorization for the bundled MCP server, if prompted by Codex.

### Install from the dev branch

The plugin has been merged to dev and is available there while awaiting a release to main. Add the repository as a marketplace:

    codex plugin marketplace add warengonzaga/suno-music-producer@dev

Restart the Codex desktop app, open **Plugins Directory**, select the Suno Music Producer marketplace, and install Suno Music Producer. Complete Suno authorization if prompted. Confirm the plugin and its Suno connection appear in Codex.

After the feature is released to main, use the stable marketplace source:

    codex plugin marketplace add warengonzaga/suno-music-producer

### First production request

Ask Codex to use Suno Music Producer for a song or cover. For a cover, identify the source track and preserve the approved lyrics and arrangement. The skill will check the existing workspace and source, verify the current model and voice options, and prepare the full prompt before generation.

## 📖 Usage

Example request:

    Use Suno Music Producer to reimagine Supernova (Reimagined) as a cover. Keep 120 BPM and Bb major, preserve the lyrics, melody, composition, arrangement, section order, and ad-libs, use Suno v6 and Stella Pinoy Pop if available, and show me the full Style prompt and lyrics for review before generation.

The skill prepares a combined Style prompt, detailed section headers, complete lyrics, and recommended supported controls. It verifies a generated clip's status and reports a song link only when Suno returns one and the result is playable.

See the [Supernova production example](plugins/suno-music-producer/skills/suno-music-producer/references/supernova-example.md) for the canonical format.

## 📚 Documentation

- [Suno Music Producer skill](plugins/suno-music-producer/skills/suno-music-producer/SKILL.md) — workflow, cover preservation, prompt construction, preflight, and result verification.
- [Supernova (Reimagined) reference](plugins/suno-music-producer/skills/suno-music-producer/references/supernova-example.md) — combined Style prompt and full section-by-section lyrics example.
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
