# Ponytail Skills Only

This is a skills-only fork of [DietrichGebert/ponytail](https://github.com/DietrichGebert/ponytail).

It keeps the Ponytail skill prompts, but removes runtime code.

## What Is Included

- `skills/ponytail`
- `skills/ponytail-review`
- `skills/ponytail-audit`
- `skills/ponytail-debt`
- `skills/ponytail-gain`
- `skills/ponytail-help`
- Minimal marketplace manifests where supported

## What Is Intentionally Removed

- lifecycle hooks
- statusline integration
- mode persistence
- local Node.js hook runtime
- Python / Hermes plugin
- Pi extension
- MCP server
- OpenCode runtime plugin
- benchmark runners
- publish scripts
- GitHub Actions workflows
- npm package metadata

## Why

The goal is to use Ponytail as prompt content only.

This reduces the local execution surface. Installing this repository should not run local scripts, start servers, write config files, call APIs, or install dependencies.

## Usage

### Codex Marketplace

Add this repository as a Codex plugin marketplace:

```bash
codex plugin marketplace add 5ei74R0/ponytail-skills
```

Install the skills-only plugin:

```bash
codex plugin add ponytail-skills-only@ponytail-skills-only
```

Remove the installed plugin:

```bash
codex plugin remove ponytail-skills-only@ponytail-skills-only
```

Remove the marketplace source:

```bash
codex plugin marketplace remove ponytail-skills-only
```

For local development from this checkout:

```bash
codex plugin marketplace add .
codex plugin add ponytail-skills-only@ponytail-skills-only
```

### Manual Skills

Install or copy the `skills/` directory into your agent's local skills directory.

Then invoke the skills manually from your agent UI.

## Limitations

This fork does not provide always-on Ponytail mode.

It does not persist `/ponytail lite|full|ultra|off`.

It does not configure a statusline.

It does not register runtime slash commands unless the host reads skill names directly from `skills/`.

## Updating From Upstream

Do not blindly merge upstream.

To update, compare only:

```text
skills/*/SKILL.md
```

Review the diff manually, then copy accepted changes.

## License

MIT. Original work by Dietrich Gebert.
