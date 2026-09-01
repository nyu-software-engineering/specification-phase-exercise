# Specification Phase Exercise

A little exercise to help you get started with the specification phase of the software development lifecycle.

## Overview

In this exercise you will work with a small team to produce the complete specification of a set of improvements and new features for **The Slide Machine** — a real, live application that you can use today at [theslidemachine.com](https://theslidemachine.com), and that is used to deliver lectures in this course.

You are not inventing an app from scratch, and you are not going to write any application code. You are joining an existing product as its next round of specification work: you will use the app, find what is missing or broken about it, decide what should be built next, and specify that work well enough that somebody else could build it.

The work to produce this specification will include:

- reviewing the existing application
- ideation
- requirements elicitation and analysis
- writing a product vision statement
- writing user stories
- UML diagramming
- rapid prototyping
- presenting your work to key stakeholders
- generating and distributing an exit-ticket quiz on your presentation

Read [background.md](./background.md) first — it explains what The Slide Machine is, who uses it, and where its existing documentation lives. Everything below assumes you have read it.

## Ground rules

Three rules shape everything in this exercise.

**You will not write application code.** Not a line of TypeScript, not a component, not a database migration. The only text files you author are Markdown documents, and the only other work you produce is design work — diagrams, wireframes, and a clickable prototype. Specification is the deliverable. If you find yourself wanting to "just build it to see if it works," that instinct is the thing this exercise is training you out of; the point is to find out whether an idea is right *before* anyone spends a month building it.

**Your work must be an improvement to The Slide Machine, not a replacement for it.** Every feature you specify has to fit the app that already exists — its user types, its vocabulary, its screens, its constraints. A specification that ignores the product it is attached to is not a specification, it is a wish.

**Your work is real.** Improvements and new features specified by student teams may be incorporated into the main project, and students whose contributions are adopted are given public credit for them. Credit is awarded only for work that is **original and not already under consideration** — an idea already specified in the project's Future Work, already raised in its Open Questions, already scheduled on the roadmap, or already proposed by someone else is not yours to be credited for. This is not a reason to avoid those areas; a genuinely new answer to an open question is exactly the kind of contribution that gets adopted. It is a reason to know what is already there before you claim it, and to say plainly in your specification what part of your proposal is new. Specify accordingly.

## Review of the existing application

Before you can improve something, you have to know it. Each member of your team must independently use the live app at [theslidemachine.com](https://theslidemachine.com) — create an account, seed a project, deliver a short spoken "lecture" of your own, watch the slides generate, edit and share the resulting deck, and look at the exit-ticket quiz that comes out of it. Do this as an instructor would, out loud, for at least a few minutes of real speech. Reading about the app is not a substitute for speaking to it.

While you do, keep notes on:

- **What is confusing.** Where did you not know what to do next, what a control did, or whether something had worked?
- **What is missing.** What did you expect to be able to do and could not?
- **What is slow, awkward, or fragile.** Where did the app make you wait, make you repeat yourself, or fail in a way you had to recover from by hand?
- **What is good and should not be broken.** The parts that work are constraints on your proposal too.

Compare your notes as a team, then write a **Review of the Current Application** into the [README.md](./README.md) file in the appropriate place: a list of your findings, each one a specific observation about a specific part of the app, and each one identified as a strength, a weakness, or a gap. Aim for at least `10` findings, drawn from more than one team member's use of the app.

Findings are observations, not solutions. "There is no way to tell whether transcription is still running after the browser tab loses focus" is a finding. "Add a status indicator" is not — that is the next section's job.

## Ideation

Ideation is often neglected. It is the process of coming up with a good idea.

In this exercise, your ideas are bounded: you must decide upon a coherent set of improvements and new features for The Slide Machine that solve specific needs you have identified in its users. Your findings from the review above are your raw material, and so are the [existing project's open questions and future work](./background.md#where-the-project-already-tells-you-what-it-does-not-know) — the places where the project has already admitted it does not know the answer are the places where your work is most likely to be adopted.

Before you can evaluate ideas, you must know whose problem you are solving. The Slide Machine already has several types of users, described in [background.md](./background.md#who-uses-the-slide-machine) — instructors who author and deliver lectures, students who receive quizzes and view shared decks, and administrators who operate the deployment. You may find that one of these types splits into sub-types with meaningfully different needs (a first-time instructor and an instructor mid-semester with sixty decks are not the same person), and you may find that your proposal introduces a user type the app does not serve today. Identify every type of user your proposal touches, and be prepared to justify any type you add.

Before you commit to an idea, find out whether the project has already had it. Read the Future Work and Open Questions sections of the Software Design Document, the delivery roadmap, and the repository's open issues and pull requests. Then write a short **Prior Art & Originality** statement into the `README.md` file in the appropriate place, saying what you checked and which parts of your proposal are new. An idea that turns out to be already specified or already scheduled is still a legitimate thing to spend this exercise specifying — your grade rests on the quality of the specification — but it will not be credited to you as a contribution, and finding that out now is much cheaper than finding it out at the demo.

Your proposal should be **substantial and coherent** — a themed body of work, not a scattering of unrelated tweaks. Some teams will deepen an area the app already has (live capture, templates, quizzes, sharing, administration); some will add an area it does not. Either is fine. A grab-bag of five unrelated small fixes is not.

## Stakeholder interview

Interview at least one person who is a good representative of each type of user affected by your proposal. These are your **stakeholders** for the purposes of this exercise.

This project has an advantage most student projects do not: its users are real and they are nearby. Instructors, teaching assistants, and students are all around you, and the course's own instructor is a stakeholder for this product. Do not interview your teammates and call it research.

Ask each of them questions about their goals, needs and desires. Find out problems and frustrations they have that this app might be able to help with — including frustrations with how they prepare, deliver, and study from lecture material today, whether or not they have ever used The Slide Machine. Where you can, sit a stakeholder in front of the live app and watch them try to use it; what they do is better evidence than what they say they would do. You should be able to identify at least four goals/needs and four problems/frustrations for each type of user.

Write details about your stakeholder(s) and their goals and frustrations into the `README.md` file in the appropriate place. Be sure to note which type of user each stakeholder represents.

## Product Vision Statement

Once your stakeholders have been interviewed, your team and they must settle on a foundational **Product Vision Statement** — a single sentence explaining the main concept of what you are proposing. The rest of your work will be based on this statement.

Because you are extending an existing product rather than inventing one, your statement must say what *your contribution* is for and whom it serves, in a way that is consistent with what The Slide Machine already is. It should be recognizable as a description of this app, and it should be specific enough that a feature which does not serve it can be identified and cut.

Write this Product Vision Statement into the `README.md` file in the appropriate place.

## User Requirements

Develop user requirements for your proposed improvements and features for each type of user. These will take the form of "user stories" - short, simple descriptions of a product feature told from the perspective of the person who wants it.

User stories follow the template,"`As a [type of user], I want [some goal] so that [some reason].`", where `[type of user]`, `[some goal]` and `[some reason]` are replaced with appropriate values. Keep them small and written in non-technical language that the type of user would use.

For each type of user you have identified, write at least `10` user stories into the `README.md` file in the appropriate place. So, for example, if you have identified three types of users, write no fewer than `30` user stories total. But your job is not to meet the minimum number. Rather, it is to write an exhaustive list of user stories for each type of user - as many as necessary to describe all the unique actions a user can take by interacting with your proposed additions to the app. There should be no obvious functionality missing from your list for any type of user. Most likely, this will mean dozens of user stories for each type of user.

Two cautions specific to this exercise. First, stories that describe functionality the app *already* has do not count toward your total — you are specifying what is new or changed, and a story that is already satisfied by the live app is not a requirement, it is an observation. Second, a feature is rarely finished by the story that introduces it: if a user can create a thing, some user must be able to find it, change it, share it, and delete it, and somebody has to be able to see what happened when it goes wrong. The stories that make a feature survive contact with real use are the ones teams forget.

## Diagrams

Draw UML Activity Diagrams showing how a user of each type uses the app to fulfill two of the user stories, from start to finish. So, for example, if you have identified three types of users, create no fewer than `6` activity diagrams.

Because your features live inside an existing app, each diagram must start where the user really starts — at a screen The Slide Machine actually has — and pass through the app's existing flow into yours. Show the unhappy paths too: the network drops, the AI provider refuses, the usage cap is reached, the user changes their mind. A diagram with only a happy path is a diagram of a demo, not of a product.

For each diagram, place the text of the corresponding user story and an image of the Activity Diagram into the `README.md` file in the appropriate place.

## Wireframe diagrams

Create a set of wireframe diagrams representing every screen of the application affected by your proposal, for all types of users. This means every new screen you are introducing, and every existing screen you are changing — for a changed screen, wireframe it as it would look after your change. Wireframes are black-and-white diagrams that show the general layout of the screen, and the content that appears on each screen, but not the actual colors, images, fonts, or other visual design elements that will be used in the final product.

Your wireframes must be consistent with the real app: the same navigation, the same names for the same things, the same places where things live. If your proposal requires renaming or moving something that already exists, that is a legitimate design decision — but say so explicitly, and be ready to defend it to a stakeholder who has already learned the current arrangement.

## Clickable prototype

Convert the wireframe diagrams into a clickable prototype. These should be complete: every link or button in the prototype should take the user to the next screen in the flow; every place where actual content will go on each screen (i.e. every bit of text, image, or video) should be represented in the wireframe diagrams used in the clickable prototype. Use as little real-looking text as possible to make it obvious what will be written in the text blocks of the final product, while not showing so much that it distracts from the abstract purpose of the wireframe diagrams.

The prototype must include enough of the app's existing screens to give your work context — a reviewer should be able to enter through a screen they recognize, reach your feature the way a real user would, and come back out. By using the clickable prototype, a non-technical person who is not closely involved with the project should be able to understand what you are proposing and how it works. Nothing should be left to the imagination.

Place a link to the published clickable prototype in the `README.md` file in the appropriate place. The link must not require a user to log in to view the prototype.

## Stakeholder demo

You will present your work during class on the exercise due date. Presentations should consist of a very brief explanation of what you are proposing and a demonstration of the clickable prototype. The entire presentation should be well organized to clearly show the core functionality of your proposal and should last no more than 5 minutes.

**You must deliver this presentation using The Slide Machine itself.** You will speak, and your slides will be generated from your speech as you speak them — that is the product you have spent this exercise specifying, and presenting with it is how you find out what it is actually like to depend on it. This is a requirement of the exercise, not a suggestion.

To do that well:

- **Seed your project ahead of time.** Give the app your topic, key terms, and any prepared material you want it to draw on — including screenshots of your prototype — so that what it generates while you speak is about your project and not about something adjacent to it. A cold, unseeded live lecture is a harder demo than you think.
- **Rehearse against the live app, not against a script.** Speak the presentation out loud at least once, in the app, and watch what it makes of you. Adjust how you speak, not just what you say.
- **Have your clickable prototype open and ready** in a separate window, so you can move between generated slides and the prototype without stalling.
- **Have a fallback.** Save or export the deck from a rehearsal run. If the live generation fails during your five minutes, fall back and keep going. Failing to plan for that is a specification failure of exactly the kind this course is about.
- **Watch it as an evaluator.** Whatever the app does to you during your demo — well or badly — is evidence about the product. Bring it to the discussion afterward.

Place a link to the deck the Slide Machine generated during your presentation into the `README.md` file in the appropriate place, after you have presented.

### Exit ticket

**After presenting, your team must generate an exit-ticket quiz from your presentation and distribute it to the rest of the class.** Use the app's own quiz generation on the deck your demo produced — that is the second half of the product, and a demo that stops at the slides has only exercised half of it.

Before you publish the quiz, review it. The generated questions come from what you actually said, which means a question that is wrong or unanswerable is telling you something about your presentation as well as about the generator. Fix what is worth fixing, and keep a note of what you had to fix.

Then distribute the quiz to your classmates in the `#specification-exercise` channel of our messaging system, and complete the exit tickets published by the other teams. This is not busywork: the point of an exit ticket is to find out how much of what you said was actually understood by the people you said it to, and the scores on your quiz are the most direct evidence you will get about whether your five minutes landed.

Place a link to the exit-ticket quiz you distributed into the `README.md` file in the appropriate place, along with a short note on what — if anything — you had to correct in the generated questions before publishing.

## Submit your work

When you are done submit your work by pushing your changes to this repository to GitHub. Then send the URL of your repository to both the graders in your personal channel and to the entire class in the `#specification-exercise` channel of our messaging system.

## Deliverables checklist

Your repository's `README.md` must contain, at minimum:

- [ ] the names of your team members, with links to their GitHub profiles
- [ ] a review of the current application — at least `10` findings, each marked as a strength, weakness, or gap
- [ ] a Prior Art & Originality statement — what you checked, and which parts of your proposal are new
- [ ] your stakeholders, the user type each represents, and at least four goals/needs and four problems/frustrations for each
- [ ] a one-sentence Product Vision Statement for your proposed contribution
- [ ] at least `10` user stories per type of user, describing new or changed functionality
- [ ] at least `2` UML Activity Diagrams per type of user, each with the text of its user story
- [ ] wireframes covering every new and every changed screen, for every type of user
- [ ] a publicly-accessible link to your clickable prototype, requiring no login
- [ ] a link to the deck The Slide Machine generated during your stakeholder demo
- [ ] a link to the exit-ticket quiz you generated from that deck and distributed to the class, with a note on what you had to correct in it
