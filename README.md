# Suno Music Producer

A Codex plugin that bundles the Suno MCP server connection and the Suno Music Producer skill.

## Install the feature branch

The plugin is currently available on the feature branch while the PR is under review. Add that branch as a marketplace:

    codex plugin marketplace add warengonzaga/suno-music-producer@feature/suno-music-producer

Then restart the Codex desktop app, open **Plugins Directory**, select the **Suno Music Producer** marketplace, and install **Suno Music Producer**. Complete Suno sign-in or authorization when prompted. Installing the plugin adds both the Suno MCP connection at https://api.suno.com/mcp and the reusable skill.

After the release is merged to `main`, add the stable repository marketplace with:

    codex plugin marketplace add warengonzaga/suno-music-producer

## What it provides

- Bundled Suno remote MCP connection at https://api.suno.com/mcp.
- suno-music-producer skill for preparing and generating songs and covers.
- Required preflight checks for existing workspace/source, Suno v6, applicable artist voice, approved BPM/key, complete prompt, and generated-song status.
- Combined Style prompt format with positive instructions and - exclusions, limited to 1,000 characters.
- Detailed, section-specific production directions in bracketed lyrics headers.
- Canonical *Supernova (Reimagined)* example at 120 BPM, Bb major, with the user's supplied section formatting.

## Repository structure

- .agents/plugins/marketplace.json — repository plugin catalog.
- plugins/suno-music-producer/plugin.json — portable plugin manifest.
- plugins/suno-music-producer/mcp.json — bundled Suno MCP endpoint and transport.
- plugins/suno-music-producer/skills/suno-music-producer/SKILL.md — reusable workflow.
- plugins/suno-music-producer/skills/suno-music-producer/references/supernova-example.md — canonical example.
