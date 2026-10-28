# ADOPTION_QUESTIONS

*Adoption questionnaire of the Universal Protocol. The answers become your project's rules
document — the one the agent reads at every session.*

---

## How to use

- **Answer before you start.** It takes 30 to 60 minutes. **Start with A and B**: they are
  the ones that make the others work. **If the acceptor and the builder are different
  people — or if the builder works without reading code —, K joins the minimum.**
- **The answers become the project rules document**, in this order: the Constitution at
  the top *(`system_prompt_recommended.md` or `system_prompt_complete.md`)*, the answers to
  this questionnaire below it, the active mode document after that.
- **An empty answer field stays empty until the answer exists.** Leave it blank and come
  back: it is more honest than "to be defined", and a blank field gets read again.
- **Where the question asks for a command, write the literal command.** Whoever will use
  it is a future session, arriving without context.
- **A named exception is a rule.** The section that stays out receives the sentence "does
  not apply, because…", written — and so it remains a decision, with a readable reason.
- The marks *(P1)*, *(P2)*… point to the corresponding protocol in
  `universal_protocol.md`, where the rule each question fits to the project lives.

## Project header

| Field | Answer |
|---|---|
| Project | |
| Answered by | |
| Date | |
| Default mode *(construction, unless said otherwise)* | |
| Last revision of these answers | |

---

## A — Authorization *(P1)*

**A1. Who authorizes change in this project?** A person, a role, a reviewing pair? If it is
you yourself, the authorization still exists — it becomes a deliberate pause between
investigating and acting.

> **Answer:**
>

**A2. Which operations require explicit confirmation beforehand, always?** The base list to
adapt: schema or migration change; deletion or full rewrite of a file read only in part;
inclusion of a new dependency; change to a contract consumed by third parties; any
operation on a real environment or real data; **alteration or removal of an existing test**
*(P4)*. *What else, in your domain, is expensive or irreversible?* (Sending a message to a
customer, billing, publishing, changing a search index, invalidating a global cache,
provisioning infrastructure.)

> **Answer** *(one operation per line)*:
>
> -
> -
> -

**A3. What is the default scope of an authorization?** One file? One module? A whole
task? *Recommended: one file at a time, until the method is up and running.* And what does
an authorization given in the chat, without a target, mean in this project? *(Recommended:
it counts as a question — it is the moment for the agent to ask for the target.)*

> **Answer:**
>

**A4. What is "the smallest change that solves it" in this project?** Is there coverage,
lint or typing pressure that will force changes beyond the request? Declare that as a
named exception — a named exception is a rule; an implicit one becomes a loophole.

> **Answer:**
>

**A5. Which code conventions must the agent follow even while disagreeing?** Names, layers,
error response format, exception handling style. *List the three that hurt most when
someone breaks them.* The disagreement, and the better path, go in `PROPOSAL`.

> **Answer:**
>
> 1.
> 2.
> 3.

**A6. Where do the secrets live, and may the agent open them?** Environment files, vaults,
variables. Say which stay **closed** to the agent, which it opens **repeating only the name
of the key**, and who makes the change when a key needs to change. *A secret named as a
secret stays out of the test.*

> **Answer:**
>
> | Where | The agent may… | Who changes it |
> |---|---|---|
> | | closed / opens and repeats only the name | |

---

## B — Reversibility *(P2)*

**B1. Where is the change record, and what is it called?** *(An append-only file at the
root is the simplest and the hardest to ignore.)*

> **Answer:**
>

**B2. Where are the physical copies, and do they go into version control?** *(Outside
version control is the usual; what matters is that they are out of the edit's reach.)*

> **Answer:**
>

**B3. Which command computes a hash on your platform, and which command reverts a file
from the copy?** Write both literally — whoever will use them is a future session, arriving
without context.

> **Answer:**
>
> ```
> hash:
> revert:
> ```

**B4. What needs to be restarted after each type of change?** The table goes into the
"restart" field of every entry in the record.

> **Answer:**
>
> | Type of change | What to restart |
> |---|---|
> | | backend / worker / frontend / nothing |

**B5. Is there a database with a write-ahead log?** If so: which is the backup API that
consolidates, and what is the procedure for writing with the service up? *(Or the decision
to write only with the service stopped.)*

> **Answer:**
>

**B6. Is there any class of file that stays outside the protocol?** Generated, `lock`,
compiled, applied migrations. **Name them explicitly** — a named exception is a rule; an
implicit one becomes a back door.

> **Answer** *(one class per line, with the reason)*:
>
> -

---

## C — Verification *(P3)*

**C1. What does your system load at boot that an isolated script still needs to load?**
Logging setup, plugin registration, environment variables, migrations, container
initialization. **That list is the mandatory header of every helper script** — with it you
measure the real environment.

> **Answer:**
>
> -

**C2. How does one find out whether the running process has the code that is on disk?**
Concrete command: process start time, version endpoint, build hash.

> **Answer:**
>
> ```
>
> ```

**C3. Where are the records that answer "what really happened"?** Application logs,
execution history, persisted messages, audit trail. **List the paths** — the rule "read the
record before forming the hypothesis" works when one knows where it is.

> **Answer** *(one path per line, with what it answers)*:
>
> -

**C4. Where does the hypothesis go, and how is it labeled?** If you have a file of pending
items or of findings, define the marker. *(`HYPOTHESIS, TO MEASURE` on the first line, with
what would settle the question.)*

> **Answer:**
>

---

## D — Tests *(P4)*

**D1. What is the command that runs the suite, and how long does it take?** If it takes
more than two minutes, also define the fast subset.

> **Answer:**
>
> ```
> full suite:                (time:       )
> fast subset:               (time:       )
> ```

**D2. How is the suite run against the old code?** `git stash`, branch, worktree, copy of
the tree. **Write the procedure down** — it is the step that proves, and the one that most
depends on being written down to happen every time.

> **Answer:**
>
> ```
>
> ```

**D3. Where does the person follow what is running?** Terminal, dashboard, live log, CI.
**If it is still to be built, that is the first item** — visibility is the brake.

> **Answer:**
>

**D4. Where are the tests, and what is the naming convention?** Include the convention for
the test that pins the conservative default.

> **Answer:**
>

**D5. What counts as refactoring without behavior change in this project?** It is the only
legitimate exemption from the rule "fails before, passes after". Define the boundary so
that it keeps being an exemption.

> **Answer:**
>

**D6. What is done with a flaky test?** How many consecutive runs prove stability, where it
is marked while in quarantine, and who decides whether it leaves the suite. *With that
written down, the procedure is a decision — and "run it again until it passes" stays out
of it.*

> **Answer:**
>

**D7. Who authorizes the alteration of an existing test, and where does the justification
live?** Changing the expected value, loosening or removing an assertion, skipping, widening
a tolerance, regenerating a *snapshot* — all of it is test alteration. *(Recommended: it
joins the A2 list; the justification goes in the altered-tests section of the acceptance
document, with the diff shown.)* And: **where does the expected value of a new test come
from in this project** — specification, recorded decision, agreed behavior — and who
decides when all three are missing?

> **Answer:**
>
> | Who authorizes altering a test | Where the justification lives | Where the expected value comes from | Who decides when there is no specification |
> |---|---|---|---|
> | | | | |

---

## E — Behavior change *(P5)*

**E1. Where does the configuration live, and is there a separation between the
repository default and the local choice?** If it is still to be created, create it: it is
what lets the default be born conservative and respect whoever has already decided.

> **Answer:**
>

**E2. What is the function that reads the live config?** Exact name. A module constant
read at import freezes the value; the function that reads at runtime is the one that
serves.

> **Answer:**
>

**E3. Which costs need a measured number before changing?** Latency, calls to a paid
service, memory use, bundle size, build time. *Define the threshold from which it becomes
someone else's decision.*

> **Answer:**
>
> | Cost | Threshold from which it is the decision of whoever pays |
> |---|---|
> | | |

**E4. How is each of those costs measured?** Concrete command. With the command written
down, "measured cost" is measured.

> **Answer:**
>
> | Cost | Command that measures it |
> |---|---|
> | | |

---

## F — Recorded decision *(P6)*

**F1. Where are the decision records, and what is the numbering scheme?**

> **Answer:**
>

**F2. Who decides?** And, more important: **which decisions belong to someone else?** Cost,
new dependency, external contract, user-visible change, vendor choice.

> **Answer:**
>
> | Decision | Whose it is |
> |---|---|
> | | |

**F3. Which non-technical constraints of your product need to be written down to stay
decided for good?** Real examples: "cannot require a service running on the user's
machine", "cannot depend on the network at boot", "cannot cost more than X per month", "has
to run offline". **These are the ones that get lost most, and the ones that cost most when
someone reopens them.**

> **Answer** *(one constraint per line, with who imposed it)*:
>
> -

**F4. Is this project a legacy migration?** If so: what is the strangling boundary (route,
module, domain), and who writes the parity criterion before each move?

> **Answer:**
>

---

## G — Pace and communication *(P7)*

**G1. Does the person follow along live or review later?** Live → one step per response,
always. Reviews later → the batch can be bigger, but the record has to be more complete,
because it is the only witness.

> **Answer:**
>

**G2. What is the expected response format?** Adapt the five-section block to your
context — the essential thing is that **what is missing to answer with certainty** has a
section of its own, that **out-of-scope findings** have another, and that **the better way
the agent saw** has a place to be read.

> **Answer:**
>
> ```
> CHANGE
> WHY
> FINDINGS
> PROPOSAL       the better way the agent saw, for whoever decides
> NEED TO SEE
> ```

**G3. What is the size limit of a proposal before it becomes an attachment?** *(The
protocol suggests 200 lines of theory.)*

> **Answer:**
>

**G4. In what language is the project written** — code, comments, commits, documents?
Keeping to that saves daily friction.

> **Answer:**
>
> | Code | Comments | Commits | Documents |
> |---|---|---|---|
> | | | | |

---

## H — AI inside the system *(P8)*

*If the product has AI, answer. If it is still without AI, write here "does not apply: the
product has no AI" and move on — a named exception is a rule.*

> **Does it apply?**
>

**H1. Which manual tasks are candidates?** For each one, the six mapping questions: who,
frequency, input, decision, what gets saved, what happens when it goes wrong.

> **Answer:**
>
> | Task | Who | Frequency | Input | Decision | What gets saved | When it goes wrong |
> |---|---|---|---|---|---|---|
> | | | | | | | |

**H2. Which of those tasks does a deterministic rule solve?** Take them off the list. **It
is usually the majority** — and it is the cheapest saving there is.

> **Answer:**
>

**H3. Which actions of your system are irreversible?** Send, pay, cancel, delete, publish,
approve. **Each of them happens with human confirmation** — write the list.

> **Answer** *(one action per line)*:
>
> -

**H4. Where do the prompts live, and what is the function that loads them?** If it is still
to be created, it is the first item — before writing the first prompt.

> **Answer:**
>

**H5. Is there hot reload of prompts?** If so, build the schema on demand — it is what makes
the edit count on the next read.

> **Answer:**
>

**H6. Where is the gate — the single point through which every tool execution passes?** If
it is still to be built, it is the first thing: **it is the gate that makes the constraint
hold.**

> **Answer:**
>

**H7. Does any tool reach other tools from the inside?** Bridge, sandbox, code executor,
sub-agent. Those escape the gate by construction — decide now what to do with them.

> **Answer:**
>
> | Tool | What it reaches | Decision |
> |---|---|---|
> | | | |

**H8. Where is the auditable record of the AI's decisions?** And does it record **the
silence** — the cases that went through without asking? *(By also recording what went
through, the question "why did this run without warning me?" gets an answer.)*

> **Answer:**
>

**H9. Where does text from outside the system's control come in** — user files, pages,
messages, search results, output of another model — **and how does that text reach the
model marked as data?** And the gate: does a tool call born from that text pass through it
like any other? *(If the answer is "the prompt says to ignore embedded instructions",
reread the law of P8.)*

> **Answer:**
>
> | Input | How it arrives marked as data | Passes through the gate? |
> |---|---|---|
> | | | |

**H10. What is the ceiling of each loop?** Calls per request, stopping condition, what
happens when it blows past the ceiling. **Write the numbers** — the ceiling is what is
written, and it is what the bill respects.

> **Answer:**
>
> | Loop | Calls per request | Stopping condition | When it blows past the ceiling |
> |---|---|---|---|
> | | | | |

---

## I — Logging *(P9)*

**I1. Do the three channels exist?** What the machine did, **what the system told the
model**, and what the model said. **If channel 2 is still to be built, that is the first
item** — it is what distinguishes a misinformed model from a model that got it wrong.

> **Answer:**
>
> | Channel | Exists? | Where |
> |---|---|---|
> | 1 — what the machine did | | |
> | 2 — what the system told the model | | |
> | 3 — what the model said | | |

**I2. Where is the single point through which every call to the model passes?** And every
tool execution? If there are many points, the work is to reduce them before instrumenting.
*(There are usually fewer doors than it seems: many "client imports" are just the type.)*

> **Answer:**
>

**I3. Do you use an SDK or a raw connection?** If an SDK: do you accept that the log stops
at what was handed to it, or will you keep both paths alive to measure the difference?

> **Answer:**
>

**I4. Which correlation fields travel on every line?** The base list: session, turn, who
asked (provider/model), intent (what triggered it), provenance (file:line). *Add what your
domain requires.*

> **Answer:**
>
> -

**I5. Who decides how much to log, and where does that decision live?** If the answer is
"it is in the code", move it to configuration. If it is in configuration that only the team
remembers exists, **take it to the owner's interface**.

> **Answer:**
>

**I6. Where do the logs live, and for how long?** File, database, both? **Dual write (file
first, database after) is the safe design.** And: are your log and the logs of third-party
libraries separate?

> **Answer:**
>

**I7. What is the secret redaction policy, and does it run before storage?** Does it import
from the system it protects? *(If so: make it neutral — one copy only.)*

> **Answer:**
>

**I8. Which questions do you want to be able to answer six months from now?** Write them
down. **They are what defines what to log.** Examples: *"why did this action run without
asking me?"*, *"which model decided this?"*, *"did the system deliver the whole text or a
cut one?"*, *"how much did this turn cost?"*

> **Answer** *(one question per line)*:
>
> -

---

## J — Session and Handoff *(P10)*

**J1. Does this work fit in one session?** If it is bigger than that — and big work is done
by sectors — **create the three artifacts before starting**: map, findings, resumption.

> **Answer:**
>
> | Artifact | Path |
> |---|---|
> | Map | |
> | Findings | |
> | Resumption | |

**J2. What are the budget limits of your window?** Number of files edited, of files read
without a finding, of sectors. **Write the numbers** — the limit is what is written.

> **Answer:**
>
> | Limit | Number |
> |---|---|
> | Files edited in the session | |
> | Files read in depth without a finding | |
> | Sectors per session | |

**J3. How does the project divide into auditable sectors?** One cohesive module, or ~10
files. A sector too big for one session is broken into subsectors in the map itself.

> **Answer:**
>

**J4. Which commands does the next session need to know by heart?** Tests, linter, type
checker, how to bring the system up. **They go in the resumption, literally** — whoever
will use them arrives without context.

> **Answer:**
>
> ```
> tests:
> linter:
> types:
> bring the system up:
> ```

**J5. Is the work file by file?** If so, adopt the handover block instead of the three full
artifacts — it is lighter and sufficient.

> **Answer:**
>

---

## K — Acceptance *(P11)*

*If the builder is the acceptor, and reads code, write that in K1 and answer K2 anyway:
approval with a record is a record; approval from memory is a report. If the builder works
without reading code, this section is the one that makes the delivery reach whoever
approves it with written evidence.*

**K1. Who is the acceptor in this project — and is it the same person who authorizes
(A1)?** If it is someone else: do they read code? The answer defines who the acceptance
document is written for, and in what language.

> **Answer:**
>
> | The acceptor | Same person as the authorizer? | Reads code? |
> |---|---|---|
> | | | |

**K2. Where is the acceptance document, and what is it called?** One file per delivery,
numbered, in its own folder and versioned with the code is the simplest design to hold
people to.

> **Answer:**
>

**K3. What does the acceptor require to see in every delivery?** The base list: the output
of each test, pasted; the output against the old code; the altered tests, with the diff and
the reason; the step by step to see it working; the delegated executions, with command and
revert. *What else, in your domain?* (Screenshot, sample data, cost measurement, the output
of a specific command.)

> **Answer** *(one item per line)*:
>
> - output of each test, pasted
> - output against the old code
> - altered tests, with the diff and the reason
> - step by step to see it working
> - delegated executions, with command and revert
> -

**K4. What does the builder perform on their own, and what do they perform with help?**
Terminal, container, environment variable, dependency installation, database, publishing.
**What they perform with help is the list of what the agent offers to do for them; what is
beyond their reach to assess is the list of what escalates to the acceptor before
executing.**

> **Answer:**
>
> | Step | Performs on their own? | The agent does it for them, after the "yes"? | Escalates to the acceptor? |
> |---|---|---|---|
> | terminal | | | |
> | container | | | |
> | environment variable | | | |
> | dependency installation | | | |
> | database | | | |
> | publishing | | | |

**K5. Which operations always escalate to the acceptor, even with the builder's "yes"?**
Publishing to production, deleting real data, paying, changing a production secret. It is
the A2 list as seen by the acceptor: what asks for their signature.

> **Answer** *(one operation per line)*:
>
> -
> -

**K6. What is the rejection criterion, written before the first delivery?** The base list:
test altered without justification; test without output against the old code; delegated
execution without a record; document written at the end, from memory; verdict filled in by
the agent. **With the criterion written, the rejection is predictable and the approval
carries weight.**

> **Answer** *(one criterion per line)*:
>
> - test altered without justification in its own section
> - test without output against the old code
> - delegated execution without command, output and revert written down
> - acceptance document written at the end
> - verdict filled in by the agent
> -

---

## What to do with the answers

1. **Assemble the project rules document:** the Constitution at the top, these answers
   below it, the active mode document after that. One file, at the root, with the name your
   project uses for that.
2. **Check the minimum that already holds:** A1, A2, A3, B1, B2, B3 and B4 answered. With
   those seven, the rule "every edit begins with the named target" already changes the
   agent's behavior in the first session.
3. **Tell the agent which mode is active.** While the mode is yet to be declared,
   construction holds.
4. **If the acceptor and the builder are different people, K1 and K2 join the minimum.**
   With them, the delivery reaches whoever approves it with evidence — and the green suite
   gains company: the output of each test and the list of altered tests.
5. **Revise when an answer actually changes.** Every revision updates the header, and an
   answer that changes because a decision was made points to the ADR that made it.

---

*© 2026 Ivana Cruz · ivana.gac@gmail.com · This document is licensed under [CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/).*
