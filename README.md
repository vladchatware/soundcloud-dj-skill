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

1. Add the SoundCloud MCP server to your opencode config. Copy
   `opencode.example.json` into `opencode.json` (project or global), or merge
   the `mcp` block manually:

   ```json
   {
     "mcp": {
       "soundcloud": {
         "type": "remote",
         "url": "https://music.vlad.chat/api/mcp",
         "enabled": true
       }
     }
   }
   ```

   For a local development instance, point the MCP URL at
   `http://localhost:3000/api/mcp` instead.

2. Install the skill with the skills CLI (installs for opencode automatically):

   ```sh
   bunx skills add vladchatware/soundcloud-dj-skill
   ```

   To install for every agent:

   ```sh
   bunx skills add vladchatware/soundcloud-dj-skill --all
   ```

3. Quit and restart opencode so the config and skill are loaded.

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