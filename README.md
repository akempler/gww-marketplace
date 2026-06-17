# gww-marketplace

A plugin marketplace for Claude Code with fun creative writing skills.

## Installation

Add the marketplace and install plugins:

```
/plugin marketplace add <path-or-repo>
/plugin install limerick-writer@gww-marketplace
/plugin install saying-of-the-day@gww-marketplace
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
