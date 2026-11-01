# Supernova (Reimagined): illustrative production example

This reference documents one user's existing Suno clip as a project-specific example. None of its artist, voice, tempo, key, model, prompt format, lyrics, or controls are global defaults for other users or projects:

- **Title:** Supernova (Reimagined)
- **Clip ID:** `1098fe23-e6da-4a84-b6c7-63f3853a0088`
- **Song URL:** https://suno.com/song/1098fe23-e6da-4a84-b6c7-63f3853a0088
- **Status at reference check:** complete
- **Approved tempo/key:** 120 BPM, Bb major
- **Voice in the Siren of the Stars example:** Stella Pinoy Pop; use it only for that project when requested or already approved, and verify the current ready voice ID
- **Model in the user's example workflow:** Suno v6; verify current availability, but do not treat it as a default for other users

The clip was retrieved through Suno MCP and returned as complete. The retrieved metadata included its lyrics and positive Style, but did not expose the model or voice used for this source clip. Verify model and voice independently for every new generation. Its existing positive Style was: “Melodic synth-pop electronica, polished crystal-clear stereo with lush spacious textures, 120 BPM breezy bounce, sweet airy youthful solo female vocals with intimate phrasing and soaring choruses, sparkling arpeggios, shimmering digital plucks, bright marimba and tropical mallet synths, airy leads, warm floating pads, smooth bouncy bass, punchy kick, crisp snares, syncopated hi-hats and light tropical percussion; intro-only melodic scratching with chopped, retriggered vocal samples; sunlit beach and clear-ocean atmosphere.”

The combined prompt below demonstrates one user's chosen Style format. It keeps that song's style identity and approved production, restores the key from the lyrics, and appends requested exclusions. It is not a general default or proof that every exclusion appeared in the original generation.

## Example combined Style prompt (one user's format)

```text
Melodic synth-pop electronica, polished crystal-clear stereo with lush spacious textures, 120 BPM, Bb major, sweet airy youthful solo female vocals with intimate phrasing and soaring choruses, sparkling arpeggios, shimmering digital plucks, bright marimba and tropical mallet synths, airy leads, warm floating pads, smooth bouncy bass, punchy kick, crisp snares, syncopated hi-hats, light tropical percussion, breezy bounce, intro-only melodic scratching with chopped retriggered vocal samples, sunlit beach and clear-ocean atmosphere, -male vocals, -deep female vocals, -duets, -choir, -rap, -acoustic guitar, -brass instruments, -aggressive EDM, -trap beats, -robotic lead vocals
```

This example combines positive instructions and dash-prefixed exclusions in one Style prompt. Other users may prefer Suno's separate Excluded Styles field. Follow the current user's preference and the live Suno fields and limits.

## Lyrics format: section-specific Suno production style

This section-by-section format is an example from one user's project. Other users can choose their own level of detail. Preserve approved lyrics and the source song's section structure for covers; do not add sections without permission.

```text
[Intro: 120 BPM, Bb major, dreamy electronica, sparkling synth arpeggios, playful melodic female vocal samples, rhythmic DJ-style scratching, syncopated vocal chopping, warm synth bass, preserve original intro hook]

[Female Vocal Scratch: Signature melodic da hook, chopped female vocal sample, DJ turntable-style scratch effects, rapid rhythmic retriggering, playful pitch variations, synchronized with soft electronic drums]
Da, da, da, da, da, da, da, da
Da, da, da, da, da, da, da, da

[Verse 1: Cute airy solo female vocals, relaxed natural phrasing, delicate synth plucks, warm ambient pads, soft electronic kick, restrained hi-hats, intimate romantic delivery, preserve original vocal melody]
In quiet night, love's a gentle breeze
Every touch, every smile, puts my heart at ease
With you, stars align, hearts beat as one
In this tender moment, love has just begun

[Chorus: Dreamy uplifting synth-pop, sweet expressive female lead, spacious shimmering synthesizers, warm rounded bass, relaxed electronic drums, sparkling arpeggios, emotional melodic hook, no aggressive dance beat]
Love is like a supernova
With you, love's pure takeover
Feels like our love is forever
Together, it's now or never

[Verse 2: Playful gentle electronica, youthful airy female vocals, mellow bouncy synth bass, delicate rhythmic percussion, shimmering bell-like plucks, warm dreamy pads, unhurried melodic delivery]
In morning light, love's a soft embrace
Every word, every laugh, fills this special place
Here, time stands still, hearts forever close
In this dance of our love, you're the one I chose

[Chorus: Warm uplifting electronic pop, bright celestial synth textures, expressive sweet female vocals, soft punchy drums, melodic sparkling arpeggios, smooth relaxed groove]
Love is like a supernova
With you, love's pure takeover
Feels like our love is forever
Together, it's now or never

[Instrumental Break: Dreamy melodic synthesizer solo, cascading celestial arpeggios, twinkling bell plucks, warm pulsing bass, gentle syncopated electronic drums, spacious magical atmosphere, no vocals, no da hook]

[Bridge: Intimate emotional solo female vocals, floating ambient synth pads, softened percussion, delicate melodic plucks, spacious reverb, gradual cinematic electronic build, sincere romantic expression]
Through the highs and lows, our love remains so strong
In each moment, we know where we belong
Under city lights, our dreams are intertwined
Our love lights the sky, shining through the night

[Chorus: Expansive uplifting synth-pop, soaring sweet female vocals, shimmering layered synthesizers, warm rounded bass, controlled electronic drums, emotional celestial atmosphere]
Love is like a supernova
With you, love's pure takeover
Feels like our love is forever
Together, it's now or never

[Final Chorus: Emotional electronic-pop climax, expansive sparkling arpeggios, lush atmospheric synth layers, gentle driving bass, expressive youthful solo female vocals, spacious uplifting arrangement, preserve original ad-libs]
Love is like a supernova (supernova, ohh)
With you, love's pure takeover
Feels like our love is forever (you're my forever, yeah)
Together, it's now or never

[Instrumental Break: Magical shimmering synth melody, delicate cascading arpeggios, gentle electronic percussion, warm dreamy bass, celestial plucks, gradual atmospheric breakdown, no vocals, no da hook]

[Outro: Soft sweet solo female vocals, intimate airy delivery, floating ambient pads, shimmering synth echoes, minimal electronic percussion, gentle dreamy fade-out]
Supernova (my love for you, oh)
Supernova (my love for you, oh)
Supernova (my love for you, yeah)
Supernova (my love for you, yeah)

[End]
```
## Example cover control values

The values audio influence `0.85`, style influence `0.70`, and weirdness `0.20` are specific to this user's example, not universal recommendations. Check the available controls and ranges, then follow the current user's preferences and goal. These values do not guarantee a musical result.
