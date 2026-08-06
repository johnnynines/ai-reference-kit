# AI Reference Kit

A set of Markdown files that teach an AI assistant who you are, how your organization works, and what your team has already decided, so you stop re-explaining your context at the start of every conversation.

Set it up once. Every conversation after that starts with the assistant already knowing your role, your stakeholders, your house style, and the decisions that are not up for debate.

## The problem this solves

Most people re-brief their AI assistant constantly. They paste the same background about their company, correct the same tone problems, and re-explain the same constraints. Then the assistant recommends something that was ruled out eight months ago, because nobody told it.

Every major AI platform now gives you three places to put context, and they behave differently:

1. **Account settings.** One instructions field that applies to every conversation you have, everywhere.
2. **A workspace.** A Claude Project, a ChatGPT Project, or a Gemini Notebook. It has its own instructions field, scoped to one kind of work.
3. **Uploaded files.** Project knowledge, a Library, a context folder. The assistant retrieves from these when a task calls for it.

Instructions belong in tiers 1 and 2. Reference material belongs in 3. Putting reference material in an instructions field makes it too long to be followed reliably. Putting instructions in uploaded files makes them easy to ignore.

This kit gives you a file for each.

## How it works

The kit has three tiers.

### Tier 1 — `general-instructions.md`

Goes in your account-level custom instructions field. This is the always-on layer: who you are, your tone, your format defaults, your language rules, and your standing rules. It applies to every conversation on the platform, inside a workspace or not.

It is deliberately short so the model actually follows it.

### Tier 2 — `project-instructions.md`

Goes in the instructions field of a single workspace. It is a scaffold you fill in per workspace, not a file you paste once. Six sections: role and scope, the context files uploaded to that workspace, standing instructions for this work, an output example, what to do when uncertain, and capability settings.

Section 2 is the important one. It is where you name each uploaded file and tell the assistant when to use it.

### Tier 3 — the numbered folders

The source material. `01` through `03` and `05` are reference the assistant retrieves from. `04` is different, and is covered in the next section.

| Folder | Contents | Update frequency |
|---|---|---|
| `01_About_Me/` | Role, communication preferences, working hours, software stack, key contacts | Rarely |
| `02_Organization/` | Company overview, org chart with stakeholder communication styles, internal glossary | A few times a year |
| `03_Active_Projects/` | Briefs for current work: objective, status, stakeholders, risks, next milestone | Monthly or per project |
| `04_Templates_and_Standards/` | Brand voice guide, email tone examples, standard report and memo structures | Rarely |
| `05_Standing_Decisions/` | Decisions log: what was decided, by whom, why, and whether it is still open | As decisions are made |

The numbering encodes reading priority, not a required upload order.

## Where `04_Templates_and_Standards/` goes

**`04` pairs with `project-instructions.md`, not with the account-level instructions.**

The other folders describe your situation. `04` defines your output: how a memo is structured, how an email opens and closes, what your written voice sounds like. That only matters inside a workspace that produces those artifacts, and it is far too long to inline.

So the three files in `04` get uploaded to the workspace itself:

- **ChatGPT, Gemini, Copilot:** add them to the Library.
- **Claude Cowork:** put them in the project's context folder.
- **Claude Projects:** add them to project knowledge.

Then list them in Section 2 of `project-instructions.md` so the assistant knows when to reach for each one. For example:

```
report-structure.md
Contains: Standard internal memo and report formats.
Use it: For any memo, brief, or report. Match the section order exactly.

email-tone-examples.md
Contains: Three annotated examples of how I write email.
Use it: Before drafting any correspondence on my behalf.
```

Without that mapping the files sit there and the assistant retrieves from them inconsistently. The mapping is what turns them from documents into standards.

## Setup

**Step 1, once per platform.** Paste your edited `general-instructions.md` into the account-level instructions field. Claude: Settings, then General. ChatGPT: Personalization, then Custom Instructions. Gemini: Personal Intelligence, then Instructions for Gemini. Copilot: personalization settings.

**Step 2, once per workspace.** Create the workspace: a Claude Project or Cowork Project, a ChatGPT Project, or a Gemini Notebook. Fill in a copy of `project-instructions.md` for that workspace and paste it into the workspace's instructions field.

**Step 3, once per workspace.** Upload the files. Always include the `04` files if the workspace produces written output. Add `01` through `03` and `05` as the work requires. A workspace focused on one client project may only need that project's brief, the org chart, and the decisions log.

Delete Section 6 of `project-instructions.md` on any platform other than ChatGPT Projects.

## Adapting it to your role

**The content is a worked example, not a template with blanks to fill.** It is built around a fictional persona: Alex Rivera, Director of Operations at Northpoint Group, a B2B consulting firm. Every name, metric, and dollar figure is sample data. Read a file to see the level of detail that makes it useful, then rewrite it as yourself.

`general-instructions.md` and `project-instructions.md` ship with placeholders in brackets, so start there only after you know what goes in them.

Work in this order:

1. `01_About_Me/my-role-and-context.md` and `my-communication-preferences.md`. These do the most work per word.
2. `05_Standing_Decisions/decisions-log.md`. Highest value per entry, because it prevents the specific failure of an assistant relitigating settled questions.
3. `02_Organization/glossary.md`. Terminology and banned words shape every draft the assistant produces.
4. `04_Templates_and_Standards/`. Rewrite these against real documents you have already sent, not idealized ones.
5. Everything else, as you need it.

Then write `general-instructions.md` from your rewritten folder content, and fill in `project-instructions.md` for your first workspace.

What makes entries useful, based on how the example files are written:

- Say what you are **not** responsible for, not just what you own. It stops the assistant from overstepping into other people's domains.
- Record the **reasoning** behind a decision, not only the decision. An assistant that knows why 78% was chosen over 80% can tell you when the reasoning stops holding.
- Give stakeholders **communication styles**, not just titles. "Prefers short written briefs, always pair a problem with a proposed resolution" changes a draft. "Managing Partner" does not.
- Keep a **banned words** list. It is the fastest way to strip the corporate register out of generated text.
- Use **real examples** in `04`. A memo you actually sent teaches format better than a description of a memo.

## Keeping it current

`general-instructions.md` restates a handful of specifics that also live in the folders, including hard thresholds and tone rules. When you change one of those in a folder file, update the instructions file too, and re-paste it. The platform holds a copy of whatever you pasted last, so edits to the file on disk do not reach the assistant until you paste them again.

Uploaded files behave differently. Most platforms hold a copy of the file as uploaded, so re-upload after editing rather than assuming the change propagated.

Date your project briefs and mark decisions as active or superseded rather than deleting them. An assistant that can see a decision was reversed, and when, is more useful than one working from a log that only shows the current state.

Stale reference material is worse than none. If a project brief has not been touched in six months, either update it or move it out of the kit.

## License

AI Reference Kit © 2026 Johnny Bilotta, licensed under [CC BY 4.0](LICENSE).

Copy it, rewrite it as yourself, and use it at work or commercially. The one condition is credit: keep an attribution line pointing back to this project in anything you publish or distribute that is built from it. Your rewritten content is yours.
