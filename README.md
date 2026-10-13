# Software Engineering Notes

> **Status: Draft v0.1 — a simple system to test and improve.**
>
> This is my personal knowledge base for learning software engineering, preparing for interviews, and finding useful explanations when I build software.

## The idea (ELI5)

Think of this repository as **one library for everything I learn about software engineering**.

- **Layer 1** is my workbench: rough notes from studying, reading, watching courses, debugging, and practising.
- **Layer 2** is my reusable knowledge collection: clear notes I have thought through and want to find again.
- **Maps** are optional signposts: short pages that point to useful starting notes.

I do **not** need to remember which technology folder contains an idea. I can search for it or follow links between related notes.

**Goal:** Spend more time understanding and using knowledge, and less time organising files.

## Repository structure (for now)

```text
software-engineering-notes/
├── README.md
├── 01-layer-1-study-notes/
│   └── 2026-10-10-authentication.md
├── 02-layer-2-knowledge/
│   ├── jwt-authentication-overview.md
│   ├── express-jwt-authentication-setup.md
│   └── jsonwebtoken-library.md
└── 03-maps/                        # optional: add maps only when needed
    └── authentication.md
```

The example filenames illustrate where notes **could** go; they are not files that already exist.

**For now, Layer 2 has no JavaScript/Node.js/Express/Security subfolders.** One idea may be relevant to several technologies. Keep the storage location simple; express relationships with links instead.

Actual software projects, exercises, and runnable applications can remain in their own repositories. This repository stores what I learn *from* them.

## The everyday workflow

```text
Learn or practise something
          ↓
Write rough notes in Layer 1
          ↓
Explain the idea in my own words
          ↓
Is there a useful, reusable idea?
       /             \
     No               Yes
     |                 |
Keep as study       Search Layer 2
history, or         for an existing note
move on                  ↓
                    Update it, or create
                    one focused note
                           ↓
                    Link related ideas
                           ↓
                    Review and apply later
```

### 1. Capture in Layer 1

Create a dated study note. Record only what helps me learn:

```md
# Study: JWT authentication

Date: 2026-10-10
Source: Course, documentation, or book + relevant link/page

## What I learned
- A JWT can carry claims and a signature.
- Express middleware can verify a received JWT.

## My questions
- What exactly does a valid signature prove?
- How is JWT authentication different from sessions?

## What I tried
- Built a protected Express route and tested it.
```

Layer 1 can be messy. It is where I work out what I understand. **Not every bullet must become a Layer-2 card.**

### 2. Decide whether an idea belongs in Layer 2

Ask:

1. **Will I want to explain, apply, or revisit this later?**
2. **Can I explain it in my own words?** If not, study or practise more first.
3. **Does a note already cover it?** Search before creating a duplicate.
4. **Is this one focused idea or several different ideas?** Split only when doing so makes the notes more useful.

Possible outcomes: **create a note**, **improve an existing note**, **leave it in Layer 1**, or **discard an unhelpful scratch note**.

### 3. Write a focused Layer-2 card

Use the card type that fits the **question** I am answering. A topic like JWT may need more than one type of card.

| Card type | Question it answers | Example |
| --- | --- | --- |
| **Concept** | What is this, why does it matter, and how does it work? | `jwt-authentication-overview.md` |
| **Setup / recipe** | How do I make this work? | `express-jwt-authentication-setup.md` |
| **Tool / reference** | What does this library/tool do, and when do I use it? | `jsonwebtoken-library.md` |

**Suggested card shape** (adapt it when useful):

```md
# JWT Authentication Overview 🟡

## Picture
A simple analogy or mental image.

## Flow
A short sequence or diagram, if useful.

## 10-second answer
One clear sentence I can say without reading.

## 60-second answer
Explain the idea in my own words.

## Tiny example
A minimal code example or scenario.

## Common mistake
One misunderstanding or failure to avoid.

## Source
Where this knowledge came from.

## See also
Links to related notes, with a short reason when helpful.
```

**For setup cards**, the 60-second explanation often works better as **Goal → Pieces → How → Failure**. Show only the essential install/config/test steps rather than forcing a pure concept explanation.

**Do not copy the template mechanically.** If a picture, flow, or example adds no value, omit it. Keep the note understandable when I read it months later.

### 4. Connect ideas by meaning

Example relationship:

```text
[JWT authentication concept]
          |
          +----> [JWT signatures]
          |
          +----> [Express JWT setup]
                         |
                         +----> [jsonwebtoken library]
```

In a Markdown file, a link might look like:

```md
## See also
- [Express JWT setup](express-jwt-authentication-setup.md) — how to implement this concept.
```

**Link when the relationship helps me understand or use something.** Do not try to link every note to everything. One note may appear in multiple contexts without being copied into multiple folders.

### 5. Find knowledge without memorising the structure

Use these in order, depending on the situation:

1. **Search** by an idea, question, filename, or code term in the repository/editor.
2. **Follow links** from a note I already know.
3. **Open a map** if a cluster of related notes has become difficult to navigate.

A map is **not a mandatory folder or a complete list of every note**. It is a small entry page. For example, `03-maps/authentication.md` might point to the core authentication overview and a few closely related notes.

**Do not create a map for every technology on day one.** Add one only when it makes retrieval easier.

### 6. Review and use the notes

- Try the **10-second answer from memory**, then explain the **60-second answer**.
- Run an example or solve a small problem when the note describes a programming skill.
- Fix mistakes, clarify explanations, and update outdated technical information.
- Keep the existing confidence colours: **🔴 unclear**, **🟡 still learning**, **🟢 good for now**.
- **🟢 does not mean “never review again.”** Revisit when the knowledge is needed or starts to fade.

The colours track my confidence and review needs; they are **my learning aid**, not a feature required by Luhmann's method.

## Rules to keep the repository manageable

1. **One software engineering knowledge repository.** Do not create separate *knowledge* repositories for each technology.
2. **Few folders, clear filenames.** Avoid nesting Layer-2 notes by technology for now.
3. **Search before creating.** Prefer correcting an existing note over making a near-duplicate.
4. **One useful point per card.** Separate concept, setup, and tool information when they answer different questions.
5. **Links must mean something.** Fewer useful links beat dozens of decorative links.
6. **Sources matter.** Record documentation URLs, book sections/pages, or course references where practical.
7. **Do not promote everything.** Layer 1 is allowed to contain material that never reaches Layer 2.
8. **Do not rebuild everything.** Move older notes only when I revisit them or have a clear reason.
9. **Improve from real problems.** Add folders, tags, automation, or new rules only if they solve a difficulty I actually encounter.

## Example: JWT across multiple subjects

Imagine I have three distinct cards:

```text
jwt-authentication-overview.md     → explains the concept
express-jwt-authentication-setup.md → explains the implementation
jsonwebtoken-library.md            → explains a specific tool
```

Later I study microservices. I do **not** need another copy of the JWT overview inside a `microservices/` folder. I can write a new note about authentication between services and link to the existing JWT concept where relevant.

## What this system is — and is not

- **Inspired by** Sönke Ahrens, *How to Take Smart Notes*: brief source notes, reusable ideas, meaningful connections, and a dependable workflow (especially Sections 1.1, 1.3, and 2.1).
- **Not a literal copy** of Niklas Luhmann's historical slip-box. The book distinguishes fleeting notes, literature notes, and permanent notes; my two layers combine some of those activities for convenience.
- **Also built for software engineering:** interview explanations, setup recipes, tool references, practical tests, and confidence reviews are my own additions.
- **Not a replacement for practice:** Writing about an API does not replace building and testing an API.

## Trial before committing

Start with **10–20 notes** from different subjects (for example HTTP, Express, JavaScript, databases). Do **not** migrate everything first.

Then check:

| Question | What success looks like |
| --- | --- |
| Can I add a new note without debating folders? | Usually yes |
| Can I find a known note quickly? | Search or links get me there |
| Can I reuse a note in another subject? | Link it instead of duplicating it |
| Can I explain and apply the idea? | The card supports recall and real practice |
| Does maintenance feel burdensome? | If yes, simplify before adding features |

**Current decision:** Keep the 2-Layer learning workflow, use one repository for software engineering knowledge, start with a shallow Layer-2 folder, and add meaningful links. Treat this as an experiment—not a permanent architecture rule.
