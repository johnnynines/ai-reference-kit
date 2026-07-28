# AI Reference Kit

A set of Markdown files that teach an AI assistant who you are, how your organization works, and what your team has already decided, so you stop re-explaining your context at the start of every conversation.

Upload it once to a Claude Project, a ChatGPT Custom GPT, or a Gemini Gem. Every conversation in that workspace starts with the assistant already knowing your role, your stakeholders, your house style, and the decisions that are not up for debate.

## The problem this solves

Most people re-brief their AI assistant constantly. They paste the same background about their company, correct the same tone problems, and re-explain the same constraints. Then the assistant recommends something that was ruled out eight months ago, because nobody told it.

A reference kit fixes this by separating two things that usually get mashed into one long prompt:

- **Standing instructions** that apply to every response (tone, format, hard rules)
- **Reference material** the assistant should retrieve from when a task calls for it (org chart, glossary, project briefs)

The first belongs in a custom-instructions field. The second belongs in project knowledge. Putting reference material in the instructions field makes it too long to be followed reliably; putting instructions in project knowledge makes them easy to ignore.

## How it works

The kit has two tiers.

**`my-ai-instructions.md`** is the distillation. Copy its contents into the custom instructions or system prompt field of any AI platform. It is deliberately short so the model actually follows it. Five blocks: who I am, how I communicate, what I use you for, standing rules, and output format defaults.

**The numbered folders** are the source material. Upload them as project knowledge, files, or attached documents. They hold the detail that is too long or changes too often to inline.

| Folder | Contents | Update frequency |
|---|---|---|
| `01_About_Me/` | Role, communication preferences, working hours, software stack, key contacts | Rarely |
| `02_Organization/` | Company overview, org chart with stakeholder communication styles, internal glossary | A few times a year |
| `03_Active_Projects/` | Briefs for current work: objective, status, stakeholders, risks, next milestone | Monthly or per project |
| `04_Templates_and_Standards/` | Brand voice guide, email tone examples, standard report and memo structures | Rarely |
| `05_Standing_Decisions/` | Decisions log: what was decided, by whom, why, and whether it is still open | As decisions are made |

The numbering encodes reading priority, not a required upload order.

## Setup

**Claude Projects.** Create a project. Paste `my-ai-instructions.md` into the project's custom instructions. Add the numbered folders' files to project knowledge.

**ChatGPT Custom GPTs.** Create a GPT. Paste `my-ai-instructions.md` into the Instructions field. Upload the folder files under Knowledge.

**Gemini Gems.** Create a Gem. Paste `my-ai-instructions.md` into the instructions. Attach the folder files as reference documents.

For any platform, add task-specific instructions on top of this foundation per project rather than editing the base file.

## Adapting it to your role

**The content is a worked example, not a template with blanks to fill.** It is built around a fictional persona: Alex Rivera, Director of Operations at Northpoint Group, a B2B consulting firm. Every name, metric, and dollar figure is sample data. Read a file to see the level of detail that makes it useful, then rewrite it as yourself.

Start here, in this order:

1. `01_About_Me/my-role-and-context.md` and `my-communication-preferences.md`. These do the most work per word.
2. `05_Standing_Decisions/decisions-log.md`. Highest value per entry, because it prevents the specific failure of an assistant relitigating settled questions.
3. `02_Organization/glossary.md`. Terminology and banned words shape every draft the assistant produces.
4. Everything else, as you need it.

Then regenerate `my-ai-instructions.md` from your rewritten folders.

What makes entries useful, based on how the example files are written:

- Say what you are **not** responsible for, not just what you own. It stops the assistant from overstepping into other people's domains.
- Record the **reasoning** behind a decision, not only the decision. An assistant that knows why 78% was chosen over 80% can tell you when the reasoning stops holding.
- Give stakeholders **communication styles**, not just titles. "Prefers short written briefs, always pair a problem with a proposed resolution" changes a draft; "Managing Partner" does not.
- Keep a **banned words** list. It is the fastest way to strip the corporate register out of generated text.

## Keeping it current

`my-ai-instructions.md` restates a handful of specifics that also live in the folders, including hard thresholds and tone rules. When you change one of those in a folder file, update the instructions file too, and re-paste it into your platform. The platform holds a copy of whatever you pasted last, so edits to the file on disk do not reach the assistant until you paste them again.

Date your project briefs and mark decisions as active or superseded rather than deleting them. An assistant that can see a decision was reversed, and when, is more useful than one working from a log that only shows the current state.

Stale reference material is worse than none. If a project brief has not been touched in six months, either update it or move it out of the kit.
