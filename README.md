# Running Coach Plugin

Claude Code plugin for personalized running and trail running coaching. Bundles skills for training planning, Garmin integration, and calendar management, along with MCP servers for persistent athlete memory and Garmin data access.

## Skills

| Skill | Description |
|-------|-------------|
| [running-coach-skill](https://github.com/barcia/running-coach-skill) | Personalized running coaching: training plans, workout feedback, nutrition, technique, and recovery |
| [garmin-skill](https://github.com/barcia/garmin-skill) | Create and upload workouts and body composition data to Garmin Connect |
| [ical-skill](https://github.com/barcia/ical-skill) | Generate RFC 5545-compliant `.ics` calendar files for training schedules |

## MCP Servers

| Server | Description |
|--------|-------------|
| Running Coach Memory | Persistent athlete memory via semantic search ([running-coach-memory-mcp](https://github.com/barcia/running-coach-memory-mcp)) |
| Garmin MCP | Access Garmin Connect data ([garmin_mcp](https://github.com/Taxuspt/garmin_mcp)) |

## Setup

### Prerequisites

- [Claude Code](https://docs.anthropic.com/en/docs/agents-and-tools/claude-code) v1.0.33+
- [uv](https://docs.astral.sh/uv/) (for MCP servers)
- Python 3.12+

### Configuration

Copy `.mcp.json` and replace the placeholder API keys with your own:

- `OPENROUTER_API_KEY` — Required for the Running Coach Memory server

### Local usage

```bash
git clone --recurse-submodules git@github.com:barcia/running-coach-plugin.git
claude --plugin-dir ./running-coach-plugin
```

If you already cloned without `--recurse-submodules`:

```bash
git submodule update --init --recursive
```

## Structure

```
running-coach-plugin/
├── .claude-plugin/
│   └── plugin.json
├── .mcp.json
└── skills/
    ├── garmin-skill/          (submodule)
    ├── ical-skill/            (submodule)
    └── running-coach-skill/   (submodule)
```

## License

[GPL-3.0](LICENSE)
