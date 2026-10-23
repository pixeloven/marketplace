# PixelOven marketplace

The single marketplace for PixelOven's Claude Code and Codex plugins.

## Install

```sh
# Claude Code
claude plugin marketplace add pixeloven/marketplace
claude plugin install crew@pixeloven

# Codex
codex plugin marketplace add pixeloven/marketplace
codex plugin add crew@pixeloven
```

Or declare it in settings:

```json
{
  "extraKnownMarketplaces": {
    "pixeloven": { "source": { "source": "github", "repo": "pixeloven/marketplace" }, "autoUpdate": true }
  },
  "enabledPlugins": { "crew@pixeloven": true }
}
```

## Plugins

| Plugin | Source | What it is |
| --- | --- | --- |
| `crew@pixeloven` | [pixeloven/crew](https://github.com/pixeloven/crew) | Portable agent methodology — 7 roles, planning/review/orchestration disciplines, onboarding + doctor. |
| `infra-skills@pixeloven` | [pixeloven/infra-skills](https://github.com/pixeloven/infra-skills) | Crew skills pack — Terraform, Ansible, Kubernetes and GitHub Actions conventions. Install beside `crew@pixeloven`. |
| `planning-skills@pixeloven` | [pixeloven/planning-skills](https://github.com/pixeloven/planning-skills) | Crew skills pack: product planning — idea shaping, requirements review, readiness, themes, story breakdown, cross-functional review. Install beside `crew@pixeloven`. |
| `identity-skills@pixeloven` | [pixeloven/identity-skills](https://github.com/pixeloven/identity-skills) | Crew skills pack: identity and auth engineering — seams, flow tracing, surface mapping, account investigation, vendor config review. Install beside `crew@pixeloven`. |
| `design@pixeloven` | [pixeloven/design](https://github.com/pixeloven/design) | The PixelOven design system — tokens, typography, brand assets. |
| `comfyui-docker@pixeloven` | [pixeloven/ComfyUI-Docker](https://github.com/pixeloven/ComfyUI-Docker) | Authoring and operating a ComfyUI model store — manifests, locks, image channels. |

Each plugin lives in its own repository. This repository holds only the
catalogue that points at them.

This catalogue is public, so it lists only public plugins. A plugin in a
private repository is added here when that repository goes public — until
then it is installed from its own repository directly.

## Why one marketplace

Marketplaces are keyed by name. A repository that publishes its own marketplace
named after itself can only ever serve that one plugin, and two repositories
cannot both claim the name `pixeloven`. So the catalogue lives here, once, and
each plugin repository stays a plugin repository.

## Releasing

Plugin entries pin a **commit SHA**, not a tag — that is the only pin a `url`
source takes. So a plugin release is two steps:

1. merge and tag the release in the plugin's own repository;
2. update that plugin's `sha` here.

Until step 2 lands, consumers keep resolving the previously pinned commit. That
is the intended behaviour: nothing ships to consumers until the catalogue says
so.

## License

MIT — see [LICENSE](LICENSE).
