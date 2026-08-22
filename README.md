# Close

**A session should not end with a list of things you now have to do.**

The failure this fixes is not forgetting things. It is the opposite — remembering them perfectly
and handing them all back. You asked for one thing, the session threw off nine more, and now they
are all yours.

Say **close**. Claude sweeps the whole session for loose ends, does every one it can, and hands
back only what genuinely needs you.

## Install

```
/plugin marketplace add charlie947/close
/plugin install close@close
```

Or drop `skills/close/SKILL.md` into `~/.claude/skills/close/`.

## What it looks for

Eight places, and the last four are the ones that get missed:

1. **Promises it made** — every "I'll", "next step", "worth fixing", "your call" in its own turns
2. **Blocked tool calls** — the permission denial it worked around and kept going
3. **Uncommitted or unpushed work** in any repo it touched
4. **Files in temp** that someone will need next week
5. **Artefacts that never arrived** — a report written but never opened, a row planned but never created
6. **Checks it reported as NOT RUN**
7. **Stale things its own work superseded** — the old version sitting next to the new one
8. **Assumptions it recorded earlier** that this session may have changed

## What it hands back

One table, three states, nothing left off:

```
CLOSED (n)
  ✓ what — the evidence, in one clause

YOURS (n) — nothing here could be done for you
  → what — why it is yours: spends money / needs your login / a guard blocked it
    the exact command to paste

PARKED (n)
  · what — why it can wait
```

Then a bare verdict on its own line, so you know whether you can walk away:

```
Good to close, ready to close.
```

It only writes that line when it is true. When something is genuinely open it says so in the same
shape and the same place, so the two are never confusable at a glance.

## The one rule that makes it work

**Evidence comes from this run.** A step is closed when a tool result from this session shows it
closed — a file written, a command that exited zero, a re-fetch that returns the new value. Not
because it ran the command and it looked fine. Claiming something is closed when it is not is the
worst outcome available, because you will act on it.

## What it will not do for you

It never touches anything that spends money, reaches another human, publishes, destroys something
real, or needs credentials only you have. Those come back as YOURS with the exact command, every
time.

## Pairs with

[save-progress](https://github.com/charlie947/save-progress) banks what the session *learned*.
Close executes what the session *left*. Run save-progress first, then close.

---

MIT. Built by [Charlie Hills](https://charliehills.substack.com).
