# Reels Script Agents

A multi-agent content workflow, built on Claude Code, that turns trending topics into recording-ready Instagram Reels scripts. It was built for the Brazilian Instagram profile of Genna Technologies (an AI social media agent), whose Reels reveal the "hidden engineering" behind companies, brands and cultural moments for an audience of social media and marketing professionals.

The workflow produced 109 topic packages (plan → script → review) between March and May 2026.

## Workflow

Four specialized agents, with a human checkpoint between each step:

```
/research ──► human picks a topic ──► /plan ──► human review ──► /script ──► human review ──► /revision ──► ready to record
```

| Step | Agent | What it does | Output |
|---|---|---|---|
| 1 | `/research` | Reads past topic folders to avoid repeats, then scans X/Twitter, Reddit and Brazilian and international news sites | 6 topic suggestions |
| 2 | `/plan` | Researches the chosen topic in depth; defines the **Big Idea** (synopsis) and the **Thesis** (plot twist) | `content/YYYY-MM-DD-slug/plano.md` |
| 3 | `/script` | Writes a timestamped script in the house format, calibrated on recent scripts | `roteiro.md` |
| 4 | `/revision` | Checks format rules, writing quality and facts | `revisao.md` |

### Script format (90–100 s)

| Section | Time |
|---|---|
| Hook | 0–6 s |
| Context | 6–18 s |
| The Big Reveal (plot twist) | 18–60 s |
| Practical application | 60–82 s |
| CTA (always mentions the brand) | 82–95 s |

## Repository structure

```
.claude/
  commands/   # slash commands: research, plan, script, revision
  agents/     # matching subagent definitions
CLAUDE.md     # project brief: audience, tone, format and workflow rules
```

The agent prompts are written in Brazilian Portuguese because the content is produced in Portuguese.

## Usage

1. Open the folder in Claude Code.
2. Run `/research` and pick a topic from the suggestions.
3. Run `/plan`, `/script` and `/revision` in order, reviewing each output before moving on.

Generated scripts (`content/`) and private reference scripts (`Old Scripts/`) are kept out of version control.

## Related

The performance side of this content (which features of a Reel drive reach) is analyzed in the companion repository `instagram-content-ml-pipeline`.
