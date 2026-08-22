---
name: close
description: >-
  Close a session out properly — find every loose end the session created and either finish it
  or hand it back as a single named decision. Use whenever the user says "close", "/close",
  "close out", "close this out", "close this session", "close this chat", "close off here",
  "are we good to close?", "can I close this?", "shall we close?", "just fix it and then we
  close", "wrap this up", "tie off the loose ends", "anything left?", "is anything left to wrap
  up here?", "what's still open?", "make sure nothing's left", "did we miss anything", "is that
  everything", or otherwise signals a session is ending and wants the residue dealt with
  rather than listed back to him.
  Runs AFTER save-progress: save-progress banks the
  LEARNINGS into canon, close executes the remaining ACTIONS. Reach for it even when he does
  not say "close" — any time a session is ending and you are about to leave work undone,
  close it out first. Not for handing work to a teammate (that is `handover`), and not for
  banking lessons on its own (that is `save-progress`).
---

# Close

The complaint this fixes, in the words of the person who asked for it: *"Sometimes you ask me to do stuff. I just want to make
sure everything's closed out that you can do."*

The failure this fixes is not forgetting things. It is the opposite — remembering them perfectly
and handing them all back. A session that ends with a nine-item list of things they now have to
do has moved the work sideways, not forward. He is the bottleneck in his own business, so every
item you hand back costs him more than it costs you.

So the job is: **find every loose end, do the ones you can, and hand back only the ones that are
genuinely his.** Then say plainly that nothing else is open.

## Run save-progress first if it has not run

Closing a session without banking what it taught you loses the durable half. If `save-progress`
has already run this session, skip it — it will have printed a receipt. If it has not, invoke it
now, then come back here. The two are a pair: save-progress writes canon, close executes actions.

## Step 1 — Find the loose ends

Read back over the whole session. Loose ends hide in eight places, and the last four are the ones
that get missed:

1. **Promises you made.** Grep your own turns for "I'll", "next step", "worth fixing", "separate
   job", "your call", "left for you", "carried forward", "still open", "not blocking", "later".
   Every one of those is an open item you created.
2. **Blocked tool calls.** A permission denial, a failed command, a timeout you moved past. You
   worked around it and kept going — it is still open.
3. **Uncommitted or unpushed work** in any repo you touched.
4. **Files in the scratchpad that should be durable.** The scratchpad is temp. Anything there that
   someone will need next week is currently scheduled for deletion.
5. **Artefacts that never reached their destination.** A report written but not opened. A Notion
   row planned but not created. A file built but its path never printed. Half-delivered is open.
6. **NOT RUN and unverified claims in anything you shipped.** If a deliverable says a check did
   not complete, that is an open item with your name on it until you have retried it once.
7. **Stale artefacts your own work superseded.** The old version sitting next to the new one, the
   index pointer aimed at a file you replaced. You created that mess this session.
8. **Loops in memory that this session touched.** If you read a project memory flagged ⚠ OPEN and
   your work bears on it, re-verify whether it is still open and say so. A memory records what was
   true when it was written; this session may have changed that.

## Step 2 — Sort each one by whether it is yours to do

One test decides it: **is it reversible, and does it follow from what they already asked for?**
If yes, it is yours — do it now, without asking. Asking permission for a reversible step that
follows from the original request is the idling he keeps correcting.

It is his, and only his, when it is one of these:

- **Spends money**, or commits him to spending it.
- **Reaches a human** — a WhatsApp, an email, a Notion page a teammate will act on.
- **Publishes** — a push to a public repo, a live post, a deploy.
- **Destroys something real** — deleting an artefact, force-pushing, dropping data.
- **Needs credentials only he has** — a vendor dashboard, an auth prompt, a 2FA flow.
- **Was blocked by a permission guard.** The guard fired for a reason. Do not route around it;
  hand back the exact command and let him run it.
- **Is a taste or positioning call.** His judgement, not yours.

Everything else is yours. Bias hard toward doing it.

## Step 3 — Do them, and prove it

Work through your list. Two things make this real rather than performative:

**Evidence comes from this run.** A step is closed when a tool result from this session shows it
closed — a file written, a command that exited zero, a re-fetch that returns the new value. Not
because you ran the command and it looked fine. If you cannot point at the result, it is not
closed, and saying it is closed is the worst outcome available, because they will act on it.

**Sweep the class, not the instance.** If you fix one stray file, one broken link, one stale
pointer, check whether the same fault exists elsewhere before calling it done. Fixing one of five
and reporting "fixed" is how the same bug comes back next week.

When something turns out to be bigger than a close-out — a real build, a decision with branches —
do not start it. Name it, and let them schedule it.

## Step 3b — The system sweep: what did this session LEARN that a tool could enforce?

*"I don't leave anything unturned. I still see stuff left unturned here, only
if it's going to improve the system, though."*

Steps 1-3 close the loose ends of the ARTEFACT. This step closes the loose ends of the SYSTEM, and
it is the half that gets skipped because nothing in the session looks like an open item.

**Walk back through every moment a tool was wrong, slow, or misleading**, and ask one question of
each: *could this be a code change instead of a note?* Four shapes, in descending order of value:

1. **A check that produced a FALSE result.** A gate that failed clean work, or passed broken work.
   You worked around it and moved on — that workaround is now load-bearing for every future session
   until the check is fixed. **Fix the check.** A false positive you merely documented will be
   rediscovered, re-diagnosed and re-worked-around by the next session, at full cost.
2. **A warning whose stated multiplier UNDERSELLS what his own data says.** You dismissed it on the
   number; the number was calibrated against a smaller or older sample. **Re-measure against the
   current export and correct the message in the tool**, so the next session weights it correctly.
3. **A tool you could not find, or an API that refused you deterministically.** N attempts with the
   same result is a capability limit, not bad luck. **Record it where the next session will look
   BEFORE trying** — including the exact forms already ruled out, so nobody spends the same four
   calls.
4. **A path, name or invocation that canon states wrongly.** Canon said a command lived somewhere it
   does not. Fix the canon line, not just your own memory of it.

**The bar is "would this change what a future session DOES".** A tidier note that no mechanism reads
is not a system improvement — it is the thing this step exists to replace. If the fix is a real
build rather than an edit, name it and let them schedule it; do not start it inside a close-out.

Everything you fix here goes in the ledger as CLOSED, with the file you changed as the evidence.

## Step 4 — The ledger

Print one table. Every item gets exactly one of three states, and nothing gets left off:

- **CLOSED** — done, with the evidence in one clause.
- **YOURS** — genuinely his, with the reason and, where it is a command, the exact line to paste.
- **PARKED** — deliberately not doing it, with why.

```
CLOSE-OUT — <session topic>

CLOSED (n)
  ✓ <what> — <evidence: the file, the exit code, the re-fetch>
  ✓ <what> — <evidence>

YOURS (n) — nothing here could be done for you
  → <what> — <why it is yours: spends money / needs your login / guard blocked it>
    <exact command or the one decision to make>

PARKED (n)
  · <what> — <why it can wait>

Nothing else is open.
```

That last line is the point of the whole skill, and it only goes in when it is true. If something
is open that you could not close and could not hand back cleanly, say what it is and why, rather
than rounding the session up to finished.

Then end on **one** next action for them — the highest-consequence item from YOURS, phrased as
a thing he can do in about two minutes. Not the whole list again. He will read the ledger; what he
needs at the bottom is where to start.

## The verdict line 

*"All I want at the end is just 'good to close, ready to close'."*

**The very last line of a close-out is a bare verdict, on its own, with nothing after it:**

```
Good to close, ready to close.
```

**Nothing follows it.** No summary, no "let me know", no restated next step, no sign-off. He has
already read the ledger above; the last line exists to answer one question — *can I walk away?* —
and anything appended to it buries the answer he actually wanted.

**It is a VERDICT, so it is only written when it is true.** When something is genuinely open, the
last line says so in the same shape and the same place, so the two are never confusable at a glance:

```
Not ready to close — <the one thing>.
```

**When he asks "can we close?" mid-session and the ledger has already been printed, the verdict line
is the WHOLE reply.** Do not reprint the table to justify it. He is asking for a yes or a no, and a
second ledger reads as not having listened. Re-verify first — a verdict recalled from earlier in the
session is a guess — then answer in one line.

## What this does not do

- It does not hand work to a teammate. That is `handover`, which writes to their board first and
  only then messages them.
- It does not bank lessons on its own. That is `save-progress`.
- It does not start new work. A loose end that turns out to be a project gets named, not begun.
- it never asks them to confirm a reversible step. If you are asking, you have already decided
  it is safe — so do it and report.
