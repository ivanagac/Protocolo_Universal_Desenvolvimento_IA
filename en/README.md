# Universal Protocol

*by Ivana Cruz · licensed under [CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/)*

*English translation of the [Portuguese original](../README.md). The original is the reference: where the two diverge, the original prevails and the divergence is a defect of this translation. The terms were fixed in [glossario_traducao.md](../glossario_traducao.md).*

A working method for developing a system with AI — both when the AI **writes** the system
and when the AI **is part** of the system.

What it does: **it gives the AI agent — which writes fast and claims with confidence — a
method to tell what it measured from what it assumed.** Everything in this repository exists
to make that difference visible — declaring before, measuring after, and keeping the two
side by side where someone can compare them.

> **A record is what was declared before and compared after. A report is what someone
> remembers having done.** You want the first.

## What is here

| File | What it is | Who reads it |
|---|---|---|
| [`universal_protocol.md`](universal_protocol.md) | The complete reference: the core in fifteen lines, the six principles, the eleven protocols (P1–P11), the table of artifacts, the usage guide, the catalog of 89 signs and ways out, and the appendix with the emulation exercise. | Whoever adopts the method and whoever writes the project's rules. |
| [`system_prompt_recommended.md`](system_prompt_recommended.md) | The lean Constitution — 65 articles, about 5,300 tokens. Duties and rights of the agent and of the authorizer. **It is the one that goes at the top of the project rules document.** | The agent, every session. |
| [`system_prompt_complete.md`](system_prompt_complete.md) | The complete Constitution — 122 articles, one per rule, with definitions, hierarchy, precedence in conflict and the end-of-response check. | The agent, when the project prefers the self-contained version; the person, to understand what each side owes and can demand. |
| [`adoption_questions.md`](adoption_questions.md) | The adoption questionnaire, fillable — 64 questions in eleven sections (A–K). The answers become your project's rules document. | Whoever owns the project, once, before starting. |

The two `system_prompt_*` files say **what always holds**; the protocol says **how it is
done**; the questionnaire makes the method **fit your project**.

## Where to start

1. Read [the core in fifteen lines](universal_protocol.md#the-core-in-fifteen-lines) and
   [the six principles](universal_protocol.md#the-six-principles). Ten minutes.
2. Answer sections **A** and **B** of [`adoption_questions.md`](adoption_questions.md). The
   others can come later; these two are the ones that make the rest work. **If the
   acceptor and the builder are different people — or if the builder works without reading
   code —, answer section K as well.**
3. Assemble the **project rules document**: `system_prompt_recommended.md` at the top, your
   answers below it, the active mode's document after that. One file, at the root of your
   project, with the name it uses for this.
4. Adopt a single rule: **every edit begins with the named target.** That changes the
   agent's behavior in the first session.
5. **P9 goes first.** If the system already runs, turn logging on now — information is
   captured at the moment it exists.

The complete order of adoption, week by week, is in the
[usage guide](universal_protocol.md#day-to-day-usage-guide).

## How the files relate

```
universal_protocol.md ............. the reference: how it is done
    │
    ├── system_prompt_recommended.md   the Constitution: what always holds ──┐
    │   system_prompt_complete.md      (one of the two goes at the top)      │
    │                                                                        ├─► the rules document
    └── adoption_questions.md ........ your project's answers ───────────────┘   of YOUR project
                                                                                      │
                                                                                      └─► mode document
                                                                                          (construction, audit…)
```

The hierarchy, from top to bottom: **the Constitution; the project rules document; the
active mode's document; the session instruction.** Each level calibrates the one above it,
within what it allows. A session instruction narrows; widening is done in writing, in the
project document. Four things cut across all modes and hold in every session: authorization
with a named target (P1), the physical copy before touching (P2), proof by execution (P3 —
with the test intact when it accuses the code, P4) and the acceptance document written
while building (P11).

## The eleven protocols

| | Protocol | The rule in one line |
|---|---|---|
| **P1** | Authorization | You read and report freely. Editing comes with the order, and the order names the target. |
| **P2** | Reversal | Physical copy, hash and declaration before touching; the declaration stays as it was written. |
| **P3** | Verification | Reading produces hypothesis; only running produces fact. Suspect the instrument before the system. |
| **P4** | Tests | A test that fails on the old code and passes on the new is proof. A test that accuses the code stays as it is; the fix goes to the cause. |
| **P5** | Behavior change | It is born switched off, with the measured cost beside it. Whoever switches it on is whoever pays. |
| **P6** | Decision (ADR) | Two solutions for the same need? Show both, list the cost, ask for the decision, and record it. |
| **P7** | Pace and communication | One state-changing step per response. "ok" answers the last thing said. |
| **P8** | AI inside the system | An instruction is a rule when verified; until then, it is a suggestion. A constraint is structure plus gate. |
| **P9** | Logging | Information is captured at the moment it exists. Log the three channels. |
| **P10** | Session and handoff | The state of the work lives on disk — that is where the next session starts from. |
| **P11** | Acceptance | Everything that is produced produces, at the same time, the evidence for the acceptor. What the person still performs with help, the agent does for them — after the "do you approve of me doing this for you?" — and leaves it written. |

Each protocol has four parts, always in the same order: **RULE**, **WHERE IT APPLIES**,
**OPERATING QUESTIONS** (the ones answered every time) and **ADOPTION QUESTIONS** (the ones
the project answers once).

## The tone: guidance, and recognition

The documents in this repository are written as **positive guidance**: each rule says what
to do, with the action verb and the target in the sentence — "edit the named target, after
the OK" —, and the force comes from precision ("only", "one at a time", "before") and from
the mechanical verification behind it.

Getting it right includes stopping. Asking for the target, the "I don't know", the pause at
the budget limit and the proposal of a better path are **the method working**, and the
documents recognize them as such. That is why every response has the `PROPOSAL` section:
the better way the agent saw — an alternative, a simplification, a path that costs less
— written for whoever decides, who reads it and answers: adopts it, or records the refusal
with the reason. Both answers are good.

## How to make the agent follow this

Three layers, from the weakest to the strongest:

1. **Instruction** — the Constitution at the top of the rules document, written as precise
   guidance — the action verb and the target in the sentence —, with the mechanical
   verification behind it.
2. **The operating questions**, run at the end of every response — the Constitution's
   end-of-response check is the short version. Ask for them to appear.
3. **Mechanical verification** — a hook that only accepts a commit with an entry in the
   record; a test that checks that every changed file has a physical copy; CI that runs the
   suite against the previous commit; CI that only accepts a change to a test file when
   there is a justification in the altered-tests section of the acceptance document; a gate
   that checks every tool call before executing it.

**An instruction is a rule when verified; until then, it is a suggestion** — the law of P8
holds for the agent too, and holds for the Constitution itself.

## If the builder does not read code

It is the most common case today: the person asks, the AI writes, and another person — who
reads code — approves. The method has three answers for it, and all three are mandatory:

- **The acceptance document** *(P11)* is written while the system is being built, from the
  first item, and goes to whoever approves: the request, what was delivered, how to see it
  working, each test with its real output and the output against the old code, **the
  altered tests in their own section**, everything the AI executed in the person's place,
  pending verification — and the verdict, which only the acceptor fills in. A delivery is
  code plus the acceptance document: the delivery is complete when the document
  accompanies it.
- **A test that accuses the code stays as it is; the fix goes to the cause** *(P4)*. When a
  test accuses the code, the AI reads the code, writes where the defect is, and only then
  touches — what is wrong, with authorization. Altering an existing test is a
  confirmation-list operation. A green suite is the absence of contrary evidence. The
  evidence is each test's output against the old code and the list of altered tests.
- **Delegated execution** *(P11)*. Container, environment variable, terminal: what the
  person still performs with help, the AI offers to do for them — explaining in their
  language what, where, what changes, how to undo and what it costs — and asks, literally,
  **"do you approve of me doing this for you?"**. One operation per question. After the yes,
  it does it, and leaves the command, the output and the revert written for the acceptor
  to read. What is irreversible, and whose consequence is beyond the person's reach,
  escalates to the acceptor before the "yes".

## What this repository leaves to your project

Everything here is generic by decision: file path, domain and identifiable system belong
to your project. Where there is an example, it is replaceable. The name, the format and
the place of each artifact — change record, ADR, map, findings, resumption — are your
project's decision, and the questionnaire exists for you to make it.

## Amendments

The Constitution and the protocol change by **recorded decision** (ADR, P6), with the
rejected options written down — the session instruction points at the friction; the
amendment is made in the document, and the reason is a pattern that repeats, with more than
one occurrence. If a step is being skipped every time, it is in the wrong place: move the
friction or automate the step, in writing — that is a welcome `PROPOSAL`.

## License and authorship

© 2026 **Ivana Cruz** — ivana.gac@gmail.com

This repository — the protocol, the two constitutions, the questionnaire and this README
— is licensed under the **[Creative Commons Attribution-ShareAlike 4.0 International
(CC BY-SA 4.0)](https://creativecommons.org/licenses/by-sa/4.0/)**. The legal text is in
[`LICENSE.md`](../LICENSE.md) and on the
[Creative Commons site](https://creativecommons.org/licenses/by-sa/4.0/legalcode).

In one line: you may copy, adapt and use it, including commercially, as long as you **give
credit**, **indicate what changed** and **distribute the derivative under the same
license**. The rules document your project generates from here is a derivative — if you
distribute it publicly, ShareAlike applies to it; internal use obliges you to nothing.

Suggested attribution:

> "Universal Protocol" (Protocolo Universal), by Ivana Cruz, licensed under
> [CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/).
