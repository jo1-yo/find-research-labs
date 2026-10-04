---
name: find-research-labs
description: Find research labs, professors, postdocs, and PhD students a student could join at their university, and turn the search into a verified contact table plus a cold-email plan. Use whenever a student asks how to get into research, which labs are hiring or undergrad-friendly, who to email about a research position, what a professor's lab works on, or wants help cold-emailing a PI — even if they only say "I want to do research" with a school and a major. Also fits grad students scouting advisors.
---

# Find Research Labs

Students lose weeks opening faculty pages one at a time, then email the wrong person at a wrong address. Do that sweep for them, carefully, and hand back something they can act on today: real people with verified contact info, what each lab actually works on, which labs show signs of welcoming students, and a plan for reaching out.

Two things make or break this:

1. **Never invent an email.** It is tempting to pattern-match `first.last@school.edu` and present it as fact. A wrong address means the student's one shot bounces or lands in a stranger's inbox. An empty cell with a link to the directory is far more useful than a plausible guess. Record an email only if you read it verbatim on a page you actually opened.
2. **Only describe papers you opened.** A student who mentions a paper the professor never wrote is finished before they start.

## Step 1 — Pin down the search

Infer from the conversation; ask one short message only for what is missing:

- University (and campus, if the system has several)
- Field and sub-interests, e.g. "CS — NLP, maybe HCI"
- Year or status, and what they have done (courses, projects, prior research)
- Constraints: paid / for credit / volunteer, in person or remote, this term or summer

If they gave a school and a major, start. Do not run an interview. If you cannot ask, state your assumptions at the top of the report and cover both routes (for-credit and direct outreach).

## Step 2 — Sweep the sources

Work from official pages outward, cheapest source first. `references/sources.md` lists where to look by discipline, the common names of undergrad-research portals, and fixes for pages that will not load; read it before searching an unfamiliar field.

1. **Department faculty directory** — the canonical list of names, titles, emails, and lab URLs. Find it with a `site:` search rather than guessing URL slugs, and harvest everything from it in one pass. Check adjacent departments too (NLP lives in CS, Linguistics, and the iSchool). If the directory renders client-side and comes back empty, look for the JSON feed behind it or fall back to a publication-database affiliation search (see `sources.md`).
2. **Recent publications** — one query per candidate PI on Google Scholar, Semantic Scholar, arXiv, DBLP, or PubMed, whichever fits the field. Open 2–3 recent papers (last ~3 years) per lab. Capture title, venue, year, original URL. Confirm the PI is actually an author on that lab's paper — a first or last author with the right affiliation — before attributing it; common names collide.
3. **Each candidate's lab page** — People, Join / Opportunities / Prospective students, Publications, News. Take the lab's own description of its focus. If the page is empty or dead, follow the directory's link to the current site or use the PI's homepage, and say which you used.
4. **University-level listings** — the undergrad research office (UROP / URAP / SURF / "Office of Undergraduate Research"), department "research for undergrads" pages, independent-study course listings and their eligibility rules, Handshake or internal job boards. Explicit "looking for undergrads" posts live here.
5. **PhD students and postdocs** — from lab People pages. They reply faster than PIs, often supervise undergrads directly, and can vouch for a student internally. Include those whose own work matches.

Aim for 8–15 labs in a broad field, fewer in a narrow one. Five labs with verified details beat twenty names. If your tool calls are limited, cut labs, not verification: cover fewer labs fully, one paper each if needed, and put the rest in the "More leads" table so the student knows what is unverified.

### What counts as undergrad-friendly

Record evidence, not a vibe:

- A section for undergraduates or prospective students on the lab page, or a live posting on the undergrad-research portal
- Undergraduate names on the People page, or an alumni list of former undergrads
- Recent papers with undergrad co-authors (lab pages often mark them with * or †)
- Assistant professors in their first few years — they are building groups and have the most open seats
- A large group — more people to supervise, more projects needing hands
- The PI teaches the undergrad course closest to their research

Note the red flags honestly too: "not accepting students", a page last updated years ago, emeritus or on leave. A time-bound statement whose window has passed ("on sabbatical through Spring 2026") gets quoted, dated, and flagged as possibly expired — tell the student to ask rather than assume.

## Step 3 — Verification rules

Apply to every row before it enters the table.

**Email.** Record it only if it appears verbatim on a page you fetched and trust: the department directory (or its data feed), the person's homepage or lab site (a site on its own domain counts when the department directory links to it), or the author line of a paper PDF from the last ~5 years. Keep the source URL beside it. Normalize obfuscated forms (`name [at] school [dot] edu`) and note the source; a CDN placeholder like "[email protected]" is unreadable, so leave it blank. If your fetch tool returns a summary instead of the page, ask it for the exact email string; if it cannot produce one, the email is unverified. If you did not see it, leave the cell blank and give the directory URL so the student can find it in ten seconds. Do not infer from the school's email pattern, from colleagues' addresses, or from memory. Do not take emails from people-search sites, RateMyProfessors, LinkedIn, or old PDFs.

**Role.** Use the title shown today: Assistant / Associate / Full Professor, Research Scientist, Lecturer, Postdoc, PhD student. When pages disagree, the department directory wins, then the person's homepage, then the lab page; note the discrepancy. Someone with recent papers but no entry in the current directory may have left — keep them out of the main table and flag them. If the only source is stale, say so ("per lab page, 2023").

**Papers.** List only papers you opened: the arXiv, PubMed, PMC, or publisher abstract page, or the PDF. Link the original — abstract page, DOI, or the PDF on the lab site — never a search-results URL. Summarize in one or two plain sentences: the problem, the approach, what they found. Write it so a sophomore can tell whether it excites them.

**Openings.** If the lab page or a portal states it, quote the key phrase with the URL and the date seen. Otherwise write "No statement found". Do not guess either way.

## Step 4 — Deliver the report

Write the report to a markdown file (`research-labs-<school>-<field>.md`, in the working directory unless told otherwise) so the student keeps it, and show the summary table in the reply. Keep the summary table scannable: one line of focus, a short openings status, one link. Quotes and extra links belong in the details.

```
# Research labs for <field> at <university>
Prepared <date>. Emails shown were read verbatim from the linked source;
a blank cell means not verified — use the directory link in the details.
<Assumptions, if you could not ask. Eligibility rules that affect this student,
e.g. unit minimums for research credit.>

## Summary table
| # | Lab / Group | Person | Role | Email | Focus | Undergrad-friendly signals | Openings | Lab page |

## Lab details
### 1. <Lab name> — <PI>, <title>
- **Lab page:** <url> · **Directory:** <url>
- **Focus:** two or three plain sentences.
- **Why it may fit you:** tie to the student's interests and skills.
- **Recent papers:**
  - [Title](original url) — venue, year. One or two sentence summary.
- **Other people to contact:** <name — role — email if verified — what they work on>
- **Openings / undergrad signals:** quoted evidence with URL, or "No statement found".

## More leads (directory-verified, lab page not opened)
| Person | Role | Email | Lab page | Directory's one-line summary |

## Where to look next
- Undergrad research portal: <url>
- Department opportunities page: <url>

## Outreach plan
(Step 5 goes here.)
```

Rank by fit first, then by accessibility: explicit undergrad program > undergrad co-authors > assistant professor > nothing. Name the 3–5 to contact first and say why. PhD students and postdocs go under "Other people to contact"; give one a row of their own only when they are the recommended first contact for that lab.

## Step 5 — Outreach plan and email template

Close the report with this. Keep the coaching short; the student will skim.

**Who to email.** The PI for small labs. For big labs, the PI *and* one PhD student or postdoc whose work matches — they answer more often and can bring the student in. One email per person, never a mass send, never two people in the same lab in the same week. If a lab page says how to apply (a form, "through UROP only"), that route replaces the cold email — following it is itself a signal.

**Template** — a scaffold, not a script:

```
Subject: Undergrad interested in <specific topic> — <name>, <year, major>

Dear Professor <Last name>,

I'm a <year> studying <major> at <school>. I read your <year> paper
"<title>" and <one specific, honest sentence: what struck you, a question
it raised, or how it connects to something you've built>.

I'd like to contribute to work in this area. I've <relevant course,
project, or skill in one sentence>, and I can commit <N> hours a week
<this term / this summer>, <for credit / as a volunteer / through <program>>.

Would you be open to a 15-minute conversation, or could you point me to
someone in your group I should talk to? My CV is attached.

Thank you for your time,
<Name>
<email> · <GitHub or portfolio link, if relevant>
```

**Say this to the student, plainly:**

- Professors get dozens of template emails a week and delete the generic ones in seconds. The email works only if the paper sentence is genuinely yours — something you read and actually thought about. Rewrite the whole thing in your own words. A hand-written, slightly imperfect email beats a polished AI one.
- Under 150 words. A specific subject line. Attach a one-page CV.
- Send Tuesday to Thursday morning, local time. No reply in 7–10 days: one short follow-up. Still nothing: move on — it is not personal.
- Do not mention other labs you contacted, and do not attach this table.

## Guardrails

- Every cell should trace to a URL you opened. If asked "are you sure about this email?", point to the page.
- Blank is a valid answer. Say what you could not verify.
- Rank by fit and the chance of a reply, not by prestige.
- Without web access, say so and deliver the search plan and template only. Never fill the table from memory.
