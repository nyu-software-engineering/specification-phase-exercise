# Background: The Slide Machine

Everything you specify in this exercise attaches to a real product. This document is your orientation to it. Read it before you start, and come back to it when you are deciding whether an idea of yours fits.

## What it is

**The Slide Machine turns the relationship between lecturer and slides on its head.** Instead of a lecturer speaking *to* slides prepared in advance, the lecturer speaks freely and the slides are generated *from* their speech, in real time, as they talk. At the end of the lecture, an "exit-ticket" quiz is generated from what was actually said and taught, distributed to students, and auto-graded.

The reason for this inversion is pedagogical, not technical. Lecture slides have become the de facto required reading for most courses, and assessments are usually built directly from them — which means a lecturer who goes "off script" to respond to a question, reorder material, or chase an idea is putting their students at a disadvantage on the quiz. So they don't. The system as it stands quietly punishes exactly the teaching that works best. The Slide Machine exists to remove that penalty: the lecturer teaches the room in front of them, and the materials follow.

The application is a full-stack TypeScript system — a React single-page app, an Express API, and MongoDB — using speech-to-text for live transcription and generative AI for slide and quiz generation.

## Where to find it

| What | Where |
| --- | --- |
| **The live application** | [theslidemachine.com](https://theslidemachine.com) |
| **The source repository** | [github.com/bloombar/slide-machine](https://github.com/bloombar/slide-machine) |
| **Software Design Document (SDD)** | `docs/SPEC.md` in the repository |
| **Delivery roadmap and phasing** | `docs/ROADMAP.md` in the repository |
| **Contributor guide** | `docs/CONTRIBUTING.md` in the repository |

You will be given lectures on how the system works internally before and during this exercise. Those lectures are themselves delivered using The Slide Machine, which means you will be watching the product you are specifying, while it is being used for its actual purpose, by its actual primary stakeholder. Pay attention to how it behaves — including when it misbehaves.

**The Software Design Document is long, and you are not expected to read all of it.** Read §1–3 (overview, goals and non-goals, personas), then read the two or three sections covering whatever area you decide to work in. Its section headings are your map of the product's territory.

## Who uses the Slide Machine

The product already recognizes these types of users. Your specification work should start from them.

- **Instructor / author** — the primary user. A registered user who creates slide projects, seeds them with prepared material, delivers live lectures, edits and shares the resulting decks, and oversees the quizzes generated from them. Their needs are reliable real-time slides, easy seeding, control over how the output looks, and confidence that what happened in the room is what students receive.
- **Student** — receives the exit-ticket quiz, and may view decks that have been shared or published. Some students are also registered authors themselves. Their needs are timely access to the quiz, prompt grading, and study material that reflects the lecture they actually attended.
- **Administrator / operator** — runs the deployment. Oversight of users and content, audited moderation, health and configuration control, and visibility into what the system is costing and whether it is working.
- **Contributor (student developer)** — students extending the system. That is you, in this exercise, in the specification role rather than the implementation one.

Whether these are the *right* user types, and whether any of them should be split into sub-types with genuinely different needs, is a question your team is allowed — and encouraged — to answer for itself.

## What the product does today

A rough map of the app's functional territory, as a starting point for your review. The Software Design Document covers each of these in detail.

- **Accounts and authentication** — sign-up and sign-in, including Google sign-in; user profiles; account types that set privacy defaults.
- **Plans, billing, and usage limits** — plan tiers, metered usage of AI and speech services, usage caps, and notifications when a cap is approached or reached.
- **Slide projects and seeding** — projects created ahead of a lecture, with prepared material (outlines, key terms, learning objectives, tone and style notes) that informs later generation; an optional "preflight" step where the instructor reviews and hones what the system expects to talk about, by UI or by voice.
- **Style template library** — the visual design system applied to generated decks, including importing a design from an existing Google Slides presentation.
- **Live lecture capture** — starting and stopping a session, real-time speech-to-text transcription, and the timestamped transcript it produces.
- **Slide generation and enrichment** — turning speech into slides as it arrives, plus automatic image sourcing to illustrate them.
- **Playback, editing, and sharing** — reviewing and post-editing a generated deck, narration playback, permalinks, and access control over who can see what.
- **Export/import, voting, and social** — getting decks in and out of other formats, and public discovery of shared decks.
- **Quiz generation** — building an exit-ticket quiz from slide content, publishing it as a Google Form, and auto-grading it.
- **Evaluation and metrics** — the telemetry the system records about its own reliability, latency, and cost, and the anonymized exports that support research on whether the approach works.
- **Administration and moderation** — the operator-facing side of all of the above.

## Where the project already tells you what it does not know

Two parts of the existing documentation are worth reading closely, because they are where your work is most likely to land:

- **Future Work** (`docs/SPEC.md` §18) — features that have been specified but deliberately deferred, each with the reasoning for why they were not built yet. If you pick one of these up, read that reasoning first; a proposal that does not engage with the stated reason for deferral will not persuade anyone.
- **Open Questions** (`docs/SPEC.md` §19) — questions the project has not resolved. These are genuine gaps in the specification, and a well-argued answer to one of them is a real contribution.

Also read the **Delivery Roadmap** (`docs/ROADMAP.md`), particularly its risks and cut-line section. Knowing what the project has decided *not* to do, and why, is how you avoid spending three weeks specifying something that was already rejected for a good reason.

## Constraints your proposal has to live within

These are not arbitrary rules of the exercise; they are real constraints on the real product, and a specification that violates them cannot be adopted.

- **Student data stays inside institutionally-approved, FERPA-compliant systems.** No student personally identifying information leaves the institution, and nothing you propose may send it to an external model. This is why, for example, quiz responses live in the instructor's own Google Workspace rather than in the application's database — a design position, not an oversight.
- **The product is discipline-agnostic.** It has to work for a history lecture as well as a computer science one. A feature that only makes sense for one field is a feature for a different product.
- **AI and speech services cost real money per use.** Every generated slide, transcribed minute, synthesized narration, and translation has a price, and the app meters and caps usage because of it. A feature that multiplies how often the system calls a model needs an answer for who pays for that.
- **Live means live.** Anything that happens during a lecture competes for the same seconds the lecturer is speaking in. Latency is a feature requirement, not an implementation detail.
- **It has to degrade gracefully.** Networks drop, providers refuse, keys expire, caps bind. A lecture in progress cannot simply stop. Specify what happens when your feature fails, not only what happens when it works.

## Why this matters beyond the grade

This exercise is part of a funded pilot of The Slide Machine in this course. Improvements and new features specified by student teams may be incorporated into the main project, and students whose contributions are adopted receive public credit for them — which is a genuinely useful thing to be able to point at in a job interview or a graduate application. The count and nature of student-contributed features is also one of the pilot's own measures of whether the system is extensible enough to be worth building.

**Credit goes only to work that is original and not already under consideration.** Before you commit to an idea, check whether the project has already got there: read the Future Work and Open Questions sections above, the roadmap, and the repository's open issues and pull requests. Something already specified, already scheduled, or already proposed by someone else can still be a perfectly good exercise to specify — you will be graded on the quality of your specification either way — but it will not be credited as your contribution. Working near those areas is fine and often smart; the requirement is that you know what is already there, and that your specification says clearly which part of it is yours.

So: specify something you would want your name on.
