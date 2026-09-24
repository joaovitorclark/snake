# snake — Acta planning repo

This directory was stamped with `acta init`. It holds the epic / feature / spec
tree. All command logic lives in the installed `acta` package.

Nothing here touches GitHub until you run `acta link`.

## Layout

```
.acta/
  acta.toml              # shared config: github repo, board, targets
  local.toml             # git-ignored: local clone path of each target
  templates/
    epic.md
    feature.md
    spec.md
.mcp.json                # the agent's entry point: acta mcp
<epic-slug>/
  epic.md
  <feature-slug>/
    feature.md
    ata.md               # append-only decision record
    specs/
      <spec-slug>.md     # the node (Acta's metadata)
      <spec-slug>/       # the payload (copied verbatim, never parsed)
```

Slugs are lowercase `[a-z0-9-]+`. `acta new` freezes `id` from the last slug.
A spec has exactly one target. Its stage is derived from pull-request facts;
there is no `state` field on a spec.

Optional user stories may live as prose under `## Acceptance Criteria` in
`feature.md`. Acta never reads that section.

## Commands

- `acta init` — how this directory was created: the stamp, `.mcp.json`, the git
  repository and the initial commit. All local; `--no-git` skips the git part.
- `acta new epic|feature|spec` — create a node from `.acta/templates/`.
- `acta brief [path]` — compile context for an agent.
- `acta ata add` — append one decision to `ata.md` (`--answers q-3` closes a question).
- `acta ata ask` — leave a question in `ata.md` for someone who is not in the conversation.
- `acta ata open [path]` — list the questions still waiting for an answer.
- `acta mcp` — serve this repo to an agent over MCP (needs `pip install "acta[mcp] @ git+https://github.com/joaovitorclark/acta.git#subdirectory=plugin"`).
- `acta ui` — open the local UI (needs the `ui` extra). Optional: everything it does, the CLI does.
- `acta spec <spec-path>` — invoke the declared authoring tool.
- `acta check [path]` — report problems in the tree (does not refuse a state).
- `acta link` — link this planning repo to GitHub and the Project v2 board.
- `acta push [path]` — project epics, features and specs as issues.
- `acta pr <spec-path>` — copy a spec's payload into a pull request on its target.
- `acta pull [path]` — fetch pull request facts into spec frontmatter.
- `acta status [path]` — show where every spec is.

`.acta/templates/` are stamps, not nodes. `acta push` skips `.acta/`.
