# find-research-labs

An agent skill that helps a student find research labs to join at their university, and reach out without wasting the one shot they get.

Give it a school and a field. It sweeps the faculty directory, lab pages, publication databases, and the undergrad-research portal, then hands back:

- a table of labs and people — professors, postdocs, PhD students — with **emails only when read verbatim from an official page**, blank otherwise with a link to check
- each lab's focus in plain language, plus 2–3 recent papers with original links and short summaries
- evidence that a lab actually takes undergrads, and any posted openings
- a cold-email template and a short, honest outreach plan

## Install

**Claude Code** — clone into your skills folder:

```bash
git clone https://github.com/jo1-yo/find-research-labs ~/.claude/skills/find-research-labs
```

Or per project, under `.claude/skills/find-research-labs/`.

**Claude.ai** — zip this folder and upload it as a custom skill in Settings.

Any agent that reads `SKILL.md` can use it the same way.

## Use

> I'm a sophomore CS major at UW interested in NLP. Help me find labs I could join.

> Which professors at Michigan do computational neuroscience and take undergrads?

The skill writes a markdown report you can keep, then walks through who to email first and how.

## Files

- `SKILL.md` — the workflow and verification rules
- `references/sources.md` — where to look, by discipline
