---
name: suno-music-producer
description: Prepare, refine, or generate Suno songs and covers using the user's established workflow, preserving source material and verifying the intended workspace, source, model, and voice.
---

# Suno Music Producer

Use this skill when the user wants to prepare, revise, or generate a Suno song or cover. Use the Suno MCP server bundled with this plugin when connected. Its configured remote endpoint is https://api.suno.com/mcp. Complete any host-managed authentication when prompted. If the MCP is not connected or unavailable, prepare a ready-to-paste brief and state that generation was not performed.

When the bundled Suno MCP connection is available, inspect its live tool schemas and allowed values rather than assuming capabilities. The installed plugin provides both this workflow and the Suno MCP connection. Never put access tokens or credentials in prompts, skill files, or plugin configuration.

## Required workflow

1. **Identify the project and source.** Use conversation context to identify the artist/project and intended original track. Search existing workspaces and the user's library. Verify the exact source clip and existing workspace before making a cover. If a workspace search is ambiguous, resolve it before generation. Never create a duplicate workspace; never create or delete a workspace without explicit permission. Do not silently move songs between workspaces.
2. **Preserve the approved song.** For reimagined covers, preserve the user's original lyrics, melody, composition, arrangement, approved BPM, key, ad-libs, and production requirements unless the user explicitly asks to change them. Do not introduce, remove, reorder, or rename song sections without permission. Suno does not automatically carry source lyrics into a cover, so pass the complete approved lyrics.
3. **Verify voice and model.** Explicitly select Suno `v6`; do not accept the default `v6-mini`. Check currently allowed model labels before generating. If v6 is unavailable, stop and report this rather than substituting another model. For Siren of the Stars, search the user's own voices for `Stella Pinoy Pop`, then loved voices if needed. Use the exact matching ready voice ID. If it is unavailable or ambiguous, do not substitute a generic voice silently.
4. **Build the combined Style prompt.** Produce one comma-separated Style prompt containing positive instructions and negative exclusions, in this order: **Genre → Production quality → BPM/key → Vocal character → Instrumentation → Rhythm → Special effects → Atmosphere → Negative exclusions**. Put every exclusion at the end with a `-` prefix (for example, `-male vocals`). Keep the entire prompt at or below 1,000 characters and count it before generation. Do not automatically move exclusions into Suno's separate Excluded Styles / `negative_style` field; leave that field unset unless the user explicitly asks to use it. Use the real track style as canonical, not an example genre from another song. See [references/supernova-example.md](references/supernova-example.md) for the exact Supernova source and a combined prompt.
5. **Write detailed lyric headers.** Every song section must contain its own section-specific Suno style and production directions inside its bracketed header. Cover vocal delivery (or explicitly no vocals), instrumentation, energy/groove, effects, and relevant restrictions; describe transitions where needed. Follow the density and section-by-section style of the Supernova reference. Preserve the user's lyric lines verbatim. Do not add song sections without permission. A closing marker such as `[End]` is not a new section.
6. **Preflight before spending credits.** Review the entire combined Style prompt, confirm its character count, complete lyrics and section headers, source clip, workspace, artist voice, v6 model, BPM/key, and supported control values. Do not submit until the requested deliverable is internally consistent and all prerequisites are verified. If a required detail conflicts or cannot be verified, stop and explain before calling a generation tool.
7. **Generate and verify.** Use the appropriate Suno MCP creation operation with the verified existing workspace. For covers, use the verified source clip and complete lyrics. Wait on every returned clip ID; report song URLs only when Suno returns them and they are playable. Distinguish a prepared prompt, submitted generation, playable result, and completed song.

## Suno MCP field mapping

- Put the complete positive-plus-negative comma-separated prompt in Suno's `style` field.
- Keep `negative_style` unset by default. Only populate it if the user explicitly asks for a separate Excluded Styles field; do not remove the `-` exclusions from the combined Style prompt.
- When supported, recommend cover controls as adjustable starting values: audio influence `0.85`, style influence `0.70`, weirdness `0.20` (85%, 70%, 20% in Suno UI). Omit unsupported controls; these values do not guarantee musical outcomes.
- Check actual allowed models, ready voice availability, source clip status, and workspace access at generation time. Do not rely on IDs or availability remembered from an earlier task.

## Output checklist

For a requested generation, the ready-to-submit brief must include the combined Style prompt, complete lyrics with production headers, title, verified source/workspace, selected voice and model, and recommended supported controls. Check all of it before consuming credits. After generation, report only verified status and returned links.
