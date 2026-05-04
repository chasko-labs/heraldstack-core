<!--
  AGENTS.md template — rendered by bin/kiro-bootstrap into <repo>/.kiro/AGENTS.md
  template placeholders use {{NAME}} syntax. lowercase ascii body, future-facing tense
-->

# kiro entry point — heraldstack-core

## what this file is

this is the kiro session entry-point doc for `heraldstack-core`. kiro loads it at session start in any session opened against this repo. its job is to declare repo identity, the haunting layers this repo inherits, and the agent slugs commonly active here. truth lives upstream in haunting-kiro-cli — this file points, never copies

## repo type

`governance`

the canonical steering for this repo type lives at `~/.kiro/steering/repo-types/governance.md` (rendered from `haunting-kiro-cli/steering/repo-types/governance.md`). conventions, deploy patterns, and default agent overlays are defined there. this overlay never re-declares any of that content

## default model

`claude-opus-4.7`

per-agent overlays in `.kiro/overlays/` may escalate model on a slug-by-slug basis (e.g. voice-critical voss work, governance-tier stratia work). the repo default applies when no overlay narrows it

## inherits from haunting

| layer            | source                                                  |
| ---------------- | ------------------------------------------------------- |
| repo-type rules  | `~/.kiro/steering/repo-types/governance.md`          |
| kb families      | governance,governance/state-taxonomy,governance/promotion-schema,governance/accepted-gaps,personas,author/voice,mcp,observability                                |
| mcp overlays     | base `mcp-core` + mcp-qdrant,mcp-observability,mcp-aws              |
| governance set   | `~/.kiro/steering/governance/`                          |
| persona profiles | `https://github.com/heraldstack/heraldstack/personas/`  |

## agents in scope for this repo

- poltergeist-stratia-aws-infra
- poltergeist-stratia-bedrock-arch
- ghost-stratia-haunting-designer
- ghost-stratia-haunting-auditor
- ghost-stratia-code-mapper
- poltergeist-kerouac-source-scribe
- ghost-scribe-style-enforcer
- ghost-orin-ci-cd
- ghost-ralph-wiggum-haunting-overlayverify
- poltergeist-lyra-aws-identity

every slug above MUST appear in the haunting capability matrix at `~/.kiro/steering/governance/capability-matrix.md`. matrix presence is the gate — a slug not in the matrix is rejected at first dispatch by `ghost-ralph-wiggum-haunting-overlayverify`

## governance tier

`high`

low — advisory + build agents, no cross-repo authority
medium — build authority within this repo, validator gate before main merges
high — governance authority, capability matrix edits, cross-collective propagation

## deploy targets

# TODO: fill in deploy targets (e.g. s3://awsaerospace.org via woodpecker)

## per-project context + scope

- `.kiro/steering/project-context.md` — what this repo is, stack, notable architectural facts
- `.kiro/steering/project-scope.md` — in-scope vs out-of-scope work + escalation patterns
- `.kiro/overlays/` — per-agent narrowings (`<base>.patch.json` + `<base>.soul.md`)
- `.kiro/mcp.overlay.json` — additional mcp servers beyond the haunting base set
- `.kiro/qdrant-metadata.json` — machine-readable project metadata, sync target for the qdrant `project-metadata` collection

## squad predecessor



(populated only when the repo migrates from the squad collective; empty otherwise)

## the rule in one sentence

this file declares identity and points upstream — every behavioral rule, every persona definition, every capability boundary lives in haunting-kiro-cli, never duplicated here