# gww-marketplace

A plugin marketplace for Claude Code with fun creative writing skills.

## Installation

Add the marketplace and install plugins:

```
/plugin marketplace add <path-or-repo>
/plugin install limerick-writer@gww-marketplace
/plugin install saying-of-the-day@gww-marketplace
/plugin install biz-dev@gww-marketplace
```

To install from a local clone, use the path to the repo root:

```
/plugin marketplace add ./path/to/gww-marketplace
```

## Plugins

### limerick-writer

Writes a custom limerick about a person given their name. The limerick follows the classic AABBA rhyme scheme and is always lighthearted and good-natured.

**Usage:**

```
/limerick-writer:limerick-writer <name>
```

**Example:**

```
/limerick-writer:limerick-writer Alice
```

> There once was a girl named Alice,
> Who drank her tea from a chalice,
> She'd sip with such grace,
> A smile on her face,
> Then nap in her book-lined palace.

### saying-of-the-day

Generates an original, pithy saying of the day. Optionally accepts a topic to tailor the saying to a specific theme.

**Usage:**

```
/saying-of-the-day:saying-of-the-day [topic]
```

**Examples:**

```
/saying-of-the-day:saying-of-the-day
/saying-of-the-day:saying-of-the-day patience
```

> *The best shortcut is the one you never need to take twice.*
>
> When you invest time doing something right the first time, you save yourself from the detour of fixing it later.

### biz-dev

Business development skills for evaluating RFPs, drafting proposals, and supporting the BD pipeline.

#### rfp-questions

Reviews an RFP (PDF) and generates a prioritized, categorized list of clarifying questions to surface gaps, ambiguities, and missing details before writing a proposal. Creates a Google Doc named `{client}-rfp-questions` via the Google Drive Connector.

**Usage:**

```
/biz-dev:rfp-questions <path-to-rfp.pdf>
```

**What it does:**
- Extracts client name, project title, and deadline from the RFP
- Analyzes scope, technical requirements, timeline, budget, staffing, evaluation criteria, legal terms, and constraints
- Generates questions rated `Critical`, `High`, or `Medium` priority
- Always includes standing questions (budget, incumbent, stakeholders, data access, acceptance criteria, out-of-scope boundary, client availability)
- Creates a formatted Google Doc with a summary table and internal notes section

**Example:**

```
/biz-dev:rfp-questions acme-proposal.pdf
```

> I've reviewed the Acme Corp RFP and created **acme-corp-rfp-questions** [link].
> I identified 18 clarifying questions: 4 Critical, 9 High, 5 Medium.
> The highest-risk areas are the undefined data migration scope (Section 4.1)
> and the absence of any stated budget ceiling.

#### rfp-proposal

Drafts a full proposal response to an RFP. Accepts the RFP PDF plus optional reference documents (Q&A responses, amendments, past performance summaries, résumés). Produces a complete, requirement-traceable proposal draft in a Google Doc named `{client}-rfp-proposal-draft`.

**Usage:**

```
/biz-dev:rfp-proposal <rfp.pdf> [reference-doc.pdf ...]
```

**What it produces:**
- **Section A — Executive Summary** (250–350 words): opening that names the solution and leads with client value, not platitudes
- **Section B — Understanding of Requirements**: paraphrased client objectives showing deep comprehension, folding in any Q&A responses
- **Section C — Features**: synthesized list of required capabilities with RFP traceability references
- **Section D — Technical Approach** (600–700 words, written for a state procurement audience): solution architecture, implementation methodology, integration & data, security & compliance, testing & QA
- **Section E — Project Timeline**: milestone table derived from RFP dates
- **Section F — Project Team & Key Personnel**: roles with qualifications drawn from any provided résumés
- **Section G — Past Performance**: up to three relevant examples mapped to evaluation criteria
- **Section H — Assumptions & Exceptions**: transparent disclosure of any gaps or deviations

Also runs a **compliance check** — every SHALL/MUST/WILL requirement from the RFP is confirmed addressed or flagged as a gap before the document is created.

**Example:**

```
/biz-dev:rfp-proposal acme-rfp.pdf acme-qa-responses.pdf
```

> Draft complete — **acme-corp-rfp-proposal-draft** [link].
> All 23 stated requirements are addressed. Two assumptions were made and flagged in Section H.
> The Past Performance section has placeholder entries — provide project details to complete.
