---
name: suno-music-producer
description: Help anyone prepare or generate Suno songs and covers by discovering their preferences, following the active project's workflow, and verifying sources and results.
---

# Suno Music Producer

Use this skill when the user wants to prepare, refine, or generate music with Suno. Use the Suno MCP server bundled with this plugin when connected. Its configured endpoint is https://api.suno.com/mcp. Complete host-managed authorization when prompted. If the MCP is unavailable, prepare a ready-to-use brief and say that generation was not performed.

Inspect live Suno MCP schemas and allowed values before relying on fields, models, voices, or controls. Never put credentials in prompts, skill files, or plugin configuration.

## Discover the user's workflow

Treat this as a personalized producer, not a preset for one artist or song.

- Start with the user's current request and relevant conversation, project, workspace, source track, and approved prior outputs. Follow direct instructions first.
- Learn preferences within their proper scope: a preference for one artist or project does not automatically apply to another. Treat examples in this skill or its references as examples, not user defaults.
- Reuse confirmed preferences for the same user and project. As songs are produced, refine a concise working profile for that artist/project: style, vocal character or chosen voice, model, tempo/key where relevant, arrangement, prompt format, section-header detail, exclusions, and controls. Treat inferred preferences as provisional, show the user the profile for correction, and refine it from their feedback. Do not claim to remember preferences across chats unless they are available in the current environment.
- For a new workflow, infer what is clear from the request, then ask only about choices that materially affect the result. Offer a concise recommendation when the user has no preference.
- Do not write a persistent preference profile or modify a workspace to store one unless the user asks.

## Song brief intake

Before drafting lyrics or generating an original song, confirm these details from the current request and project context:

1. **Subject:** What is the song about?
2. **Story:** What happens, in a short high-level summary, and where should the story or emotion land?
3. **Genre:** What musical genre should guide the song?
4. **Vibe:** What mood or feeling should it carry?
5. **Language:** What language should the lyrics use, or should it be instrumental with no vocals?

Reuse details the user already gave. Ask one concise, bundled follow-up for only the missing details; do not start writing lyrics or call a generation tool until the brief is clear. If the user is unsure about a nonessential choice, offer a fitting option for them to accept or change. Do not treat examples or inferred preferences as confirmed answers.

For a faithful cover, use the verified source to establish its subject, story, and lyric language, and ask only about changes the user wants. For a reimagined cover, confirm the requested genre, vibe, and language if they are changing. For an instrumental, record the language as “instrumental / no vocals” and establish its subject or scene plus genre and vibe before generation.

## Songwriting

This skill can write original songs as well as prepare lyrics for Suno. Discover how the current songwriter wants to work; do not make one creator's method the default.

- Follow the requested collaboration style. If the user asks for a complete draft, provide a complete draft. If they prefer co-writing, work at the requested pace and lock sections they approve. Ask only when the desired process or a missing story detail materially affects the lyrics.
- For original songs, develop the idea into a clear premise, emotional direction, title or hook, suitable song structure, and original lyrics. Match language, point of view, genre, tone, audience, and lyric detail to the user's request and active project.
- Let the user choose the structure and writing method. A chorus-first, story-driven, section-by-section approval process is available as one optional method in [references/story-driven-songwriting.md](references/story-driven-songwriting.md); use it only when the user selects it or their confirmed project preferences call for it.
- Check narrative consistency, natural phrasing, rhyme, meter, and singability for every original lyric draft. Unless the songwriter requests free verse or another approach, choose an intentional syllable pattern and rhyme scheme for each section before polishing it. Count syllables by natural pronunciation, and keep lines that share a melodic phrase rhythmically consistent. Treat the target as a guide when a natural sung pronunciation or the melody calls for a small variation; never force filler, awkward syntax, or a false story fact to meet a count or rhyme.
- Keep lyric formatting clean and readable: put each line on its own, separate stanzas with a blank line, and use a blank line after line 4 of any 8-line chorus so it reads as two four-line halves. Preserve that break in repeated choruses and in Suno-ready lyrics.
- Keep syllable counts and rhyme letters out of the lyric text. When presenting an original draft, add a compact craft note outside the lyrics with each section's syllable pattern and rhyme scheme; call out any intentional variation. Do not add those notes to the Suno lyrics field.
- Preserve user-approved lyrics. Do not silently rewrite approved sections or alter supplied lyrics unless asked.
- Keep writing and production separate. Once lyrics are approved, shape Suno's Style prompt, section-specific production headers, vocal delivery, instrumentation, and arrangement around them. Do not rewrite lyrics just to fit a new production direction.
- Write original material; do not copy lyrics from other songs or claim the words are by a named artist.

## Required workflow

1. **Identify the project and source.** Determine the intended artist/project and track from the request and available context. For original songs, complete the song brief intake before drafting lyrics or generating. For covers, find and verify the exact source clip and its existing workspace before generation. Resolve ambiguous matches first. Never create duplicate workspaces; never create or delete a workspace without explicit permission. Do not silently move songs between workspaces.
2. **Preserve the source when requested.** For original songs, use the songwriting workflow above. For reimagined covers, preserve the user's approved lyrics, melody, composition, arrangement, section order, ad-libs, tempo, key, and production requirements unless the user asks to change them. Do not add, remove, reorder, or rename sections without permission. Pass the complete approved lyrics when the Suno operation requires them.
3. **Select model and voice for this project.** Check currently available model and voice options. Use a model or named voice the user requested, or an approved choice already established for this same project. Do not force a single model, artist voice, tempo, key, genre, or prompt format as a universal default. If no choice is established, recommend an available option that fits the user's goals; ask only when the choice materially changes the desired result. Use an exact ready voice match, and never substitute another voice silently. Do not create or modify a voice unless the user asks.
4. **Prepare Suno prompts in the user's format.** Discover whether the user prefers exclusions combined in the Style prompt or entered in Suno's separate Excluded Styles field, and follow the preference when the live interface supports it. Do not treat a format shown in an example as mandatory. If no format preference is known, use the supported fields in a clear, conventional way. Keep each prompt within Suno's current field limits and count characters when a limit applies.
5. **Write song-specific lyrics and section directions.** Preserve approved lyric lines verbatim. Use the user's preferred format for bracketed section headers. Apply the lyric craft and formatting checks above before delivery. When detailed production directions are wanted, make each song section's header specific to that section; cover vocal delivery (or no vocals), instrumentation, energy/groove, effects, transitions, and restrictions where relevant. Do not add sections without permission.
6. **Preflight before using credits.** Confirm the complete brief against the user's request: title, source and workspace, lyrics, section order, tempo/key, project preferences, prompt fields, available model/voice, and supported controls. Do not call a generation tool if a required fact is ambiguous or the prompt conflicts with an approved requirement. Generate only when the user has requested generation.
7. **Generate and verify.** Use the appropriate Suno MCP operation with the verified source and workspace. Wait for every returned clip ID to reach a final status. Share a song link only when Suno returns it and the result is playable. Distinguish a prepared brief, submitted generation, playable result, and completed song.

## Controls and project preferences

- Check live schemas for supported Style, Excluded Styles, model, voice, and control fields.
- Follow the user's established prompt format. Keep positive and negative instructions in the fields the user prefers and the current Suno interface supports; avoid duplicating or contradicting exclusions across fields.
- Discover supported control ranges and the user's goal (for example, source fidelity or experimentation). Recommend task-appropriate starting values only when useful; do not impose fixed percentages as universal defaults.
- Summarize the choices used for the project so the user can correct them. Ask before saving them to a persistent file or workspace.

## Output checklist

For an original songwriting request, provide the requested concept, title or hook, structure, lyrics, and collaboration notes. For a generation request, prepare the complete lyrics with the requested section directions, the selected prompt format, title, source/workspace when applicable, current model and voice choice, and supported controls. Make any unresolved assumptions visible before generation. Afterward, report verified status and returned links only.
