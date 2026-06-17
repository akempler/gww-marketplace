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
