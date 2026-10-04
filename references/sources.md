# Where to look

Official university pages first; databases for papers; everything else is a hint to verify.

## Any field

- **Department faculty directory** — "People", "Faculty", "Directory". Search `site:<school>.edu <department> faculty`. This is where titles and emails come from.
- **Lab pages** — linked from the directory, or `"<PI name>" lab site:<school>.edu`.
- **Undergrad research office** — common names: UROP, URAP, SURF, Office of Undergraduate Research, Undergraduate Research Center. Search `site:<school>.edu undergraduate research opportunities <department>`. Postings here are the clearest "we take undergrads" signal.
- **Course-credit research** — independent study / directed research course numbers (often 199, 299, 399, 499). The course page sometimes lists faculty who take students.
- **Internal job boards** — Handshake (usually needs a login; tell the student to check), department "student jobs", work-study listings.
- **Google Scholar profile** — recent output and co-authors; undergrad co-authors show up here.
- **Semantic Scholar API** — `api.semanticscholar.org/graph/v1/author/search?query=<name>&fields=papers.title,papers.year,papers.externalIds` returns JSON with DOIs and arXiv IDs, handy for canonical links and for labs whose publications page will not render.
- **PubMed E-utilities** — `eutils.ncbi.nlm.nih.gov/entrez/eutils/esearch.fcgi?db=pubmed&term=<name>[Author]+<school>[Affiliation]` then `efetch.fcgi?db=pubmed&id=<ids>&rettype=abstract` gives abstracts in one call per PI. Limit: 3 requests per second without an API key.
- **Grants** — NSF award search (`nsf.gov/awardsearch`), NIH RePORTER (`reporter.nih.gov`). A funded lab can pay undergrads; a new grant means new projects.

## Computer science · EE · robotics

- DBLP (`dblp.org/search?q=<name>`) — complete publication list with venue, year, DOI/arXiv links.
- arXiv — open PDFs; author search works well for active researchers.
- CSRankings (`csrankings.org`) — faculty per research area per school; a fast first pass on who works on NLP / vision / systems / HCI at a given university.
- OpenReview — ML conference papers.

## Life sciences · medicine · neuroscience · psychology

- PubMed (`pubmed.ncbi.nlm.nih.gov/?term=<name>[Author]+<school>[Affiliation]`) — canonical; links to DOI and free full text on PMC.
- bioRxiv, medRxiv, PsyArXiv — preprints.
- Medical schools often keep separate profile systems (`profiles.<school>.edu`, "Scholars@…") that show emails and lab membership.

## Physics · chemistry · math · engineering

- arXiv (physics, math), ChemRxiv, IEEE Xplore, ACS Publications.
- Math: zbMATH / MathSciNet for publication lists; REU-style summer programs on department pages.
- Engineering departments frequently run their own summer undergrad research programs — check the department's "Undergraduate research" page.

## Social sciences · humanities · business · policy

- Google Scholar, SSRN (economics, law, finance), NBER working papers, PhilPapers.
- Research-assistant positions here are often paid and posted on department pages or the school job board: `site:<school>.edu "research assistant" <department>`.
- Centers and institutes ("Center for …", "Institute of …") often matter more than departments; check their People pages.

## When a page will not load

- **Directory shows no names** — it is rendered client-side. Look in the page source for the script bundle or a JSON endpoint (often `/api/...people...`) and fetch that; otherwise search by affiliation in Google Scholar or PubMed and rebuild the list from the papers.
- **Fetch tool fails on TLS or returns 403** — try `curl -sL` from the shell; if the publisher blocks you, use the PubMed, PMC, or arXiv record of the same paper and link the DOI.
- **Fetch tool returns a summary, not the page** — ask it explicitly for the verbatim email string or quote. If it cannot, treat that field as unverified.
- **Author name matches several people** — check author position and affiliation on the paper before attributing it to a lab.

## Reading a lab page quickly

- **People / Members / Team** — roles and emails; look for an Undergraduates heading or an alumni list.
- **Join / Opportunities / Prospective students / FAQ** — the openings statement, and how they want to be contacted. Some say "email with CV and transcript", some say "apply only through UROP". Pass that on; following it is a point in the student's favor.
- **Publications** — the lab's own list, often with PDFs and starred undergrad authors.
- **News** — new hires, grants, "welcome X" posts show the lab is alive.

## Email verification

Acceptable sources: department directory, lab People page, the person's homepage on a university domain, author line of a paper PDF from the last ~5 years. Obfuscated forms (`name at school dot edu`, an image) count once you have read and normalized them — note the source.

Not acceptable: the school's email pattern applied to a name, people-search sites, RateMyProfessors, LinkedIn, memory.
