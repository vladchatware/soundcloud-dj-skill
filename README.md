# soundcloud-dj-skill

An opencode skill that turns any agent into an autonomous SoundCloud DJ. It
drives the **SoundCloud MCP server** from [music.vlad.chat](https://music.vlad.chat)
to discover tracks, queue background analysis, compare candidate evidence, and
keep a lasting live set moving with momentum and vibe control.

The skill distills the DJing policy and discovery discipline that powers
music.vlad.chat's autonomous DJ: lasting-set continuity, energy arcs,
harmonic (Camelot) mixing, tempo discipline, and the
discover → schedule → compare → commit loop.

## Install

1. Clone this repo somewhere stable, e.g. `~/Projects/soundcloud-dj-skill`.

2. Add the SoundCloud MCP server and the skill path to your opencode config.
   Copy `opencode.example.json` into `opencode.json` (project or global), or
   merge the two blocks manually:

   ```json
   {
     "mcp": {
       "soundcloud": {
         "type": "remote",
         "url": "https://music.vlad.chat/api/mcp",
         "enabled": true
       }
     },
     "skills": {
       "paths": ["~/Projects/soundcloud-dj-skill/soundcloud-dj"]
     }
   }
   ```

   The skill folder is `soundcloud-dj/` inside the repo — the skill name
   `soundcloud-dj` must match its folder name. For a local development
   instance, point the MCP URL at `http://localhost:3000/api/mcp` instead.

3. Quit and restart opencode so the config is reloaded.

## Use

Ask for a mix in natural language:

- "Play hidden gems from my likes or similar tracks."
- "Keep the pressure but make the next move heavier."
- "Turn toward wetter, stranger textures while keeping a rhythmic thread."

The skill teaches the agent the MCP tool usage, musical policy, discovery and
queue discipline, momentum/vibe control, and the advanced performance-score
mode.

## MCP tools

`likes`, `tracks`, `playlists`, `track_analysis`, `compare_track_analysis`,
`schedule_track_analysis`. See `SKILL.md` for the full contract.

## Development

- `SKILL.md` — the skill body (source of truth for DJing behavior).
- `opencode.example.json` — example opencode wiring for the MCP + skill.

The skill is plain markdown; edit and push to update all consumers.

## License

MIT