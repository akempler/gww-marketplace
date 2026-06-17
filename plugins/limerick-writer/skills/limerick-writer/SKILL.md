---
name: limerick-writer
description: Use this skill when the user asks for a limerick, wants a funny poem about someone, or provides a person's name and asks for a limerick. Trigger phrases include "write a limerick", "limerick about", "funny poem for", or "make a limerick".
---

# Limerick Writer

Write a limerick about the person whose name the user provides.

## Instructions

1. The user will provide a person's name via `$ARGUMENTS` or in their message.
2. Compose an original limerick (AABBA rhyme scheme, 5 lines) that:
   - Uses the person's name in the first line
   - Is lighthearted and good-natured — never mean-spirited
   - Finds a creative rhyme for the name
   - Tells a tiny, amusing story
3. Present the limerick cleanly, with each line on its own line.
4. If the user doesn't provide a name, ask for one before writing.

## Arguments

The user's input: $ARGUMENTS

## Example

If the user says `/limerick-writer:limerick-writer Alice`, respond with something like:

There once was a girl named Alice,
Who drank her tea from a chalice,
She'd sip with such grace,
A smile on her face,
Then nap in her book-lined palace.
