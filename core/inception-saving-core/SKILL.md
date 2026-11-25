---
name: inception-saving-core
description: Use only in Claude projects whose instructions say "Part of Inception" (formerly inception-saving): starting a session, saving work to the project's files ("save", "RS"), loose ends ("LE"), housekeeping ("HK"), check email ("CE"), wrap up ("WU"), moving to a new chat, starting a new module, and "check for updates".
---

# Inception: Saving Between Chats (Core)

**Core skill, Inception alpha 0.7 (11/25/2026).** Part of Inception's Core (formerly `inception-saving`). Don't edit this file: the owner's own changes go in their settings (the "Inception settings" block and the Inception project's `claude/my-changes.md`) and win over this skill.

**Where this applies:** only in projects whose instructions say "Part of Inception".

## Why
Claude doesn't remember between chats, and long chats get compressed. **The project's files are the single source of truth.** Anything not written to a file can be lost.

## Each project's files
- **`claude/manual.md`**: what this project is for, its rules, people, accounts and where things live. Read it in full at the start of every chat. **Keep it short (about two pages):** it's read every chat, so history goes to the decisions file and finished work leaves the to-do. Suggest trimming when it grows past that.
- **`claude/todo.md`**: open items only, each numbered `#N` with a priority: **P1** urgent (a date within about a week, money or a legal date at stake), **P2** this month, **P3** later. Put any due date up front: `#12 P1 (due 11/20) Send the appeal letter`. Ask before adding an item.
  - **Numbers are stable labels:** a new item takes the next number; never renumber unless the owner says so, and never reuse an old number.
  - **Each item stands on its own:** what, why, next step.
  - **Closing an item:** strike it through with a dated note (`~~#12 …~~ done 11/20`), then move it to the decisions file at the next save.
  - Re-check P1/P2/P3 at every save (a due date coming closer moves an item up).
- **`claude/decisions.md`**: decisions and answers, dated and attributed ("(Sam, 11/8)").
- Small projects can keep everything in `manual.md`.
- **The Inception project itself** (the home project): `claude/my-changes.md` is its manual. It holds the owner's settings, project list, rules and change log.

## Starting a chat
Read `manual.md` in full and the to-do. Ask what they want to work on. Don't pitch extra work.

## Saving
- **Don't rewrite the files on every message.** Keep track in the chat, and save when the owner says **"save"**, **HK** or **WU**, and on your own after each finished piece of work (a decision made, a message sent, a document built) or about every hour in a long chat. Say "Saved" in one line.
- **Read the current file first and merge into it.** Nothing already written may be lost.
- **Facts, not guesses:** write only what people actually said or did, attributed. A useful inference is labeled "Assumption (Claude, from context): …".
- **No silent deletions:** mark replaced rules "(replaced <date>)"; log removals in the decisions file.
- **Backups, once a day before the first rewrite of a file:** save an exact copy as `claude/backups/YYMMDD_<file>.md` in the same project. Copy the file as-is (upload it from a file if your tools allow); never retype it from memory. Keep 7 days.
- **Never store** passwords, full card or account numbers (last 4 digits only), or ID numbers.
- **Saving fails** (no way to write project files): say so at once, give them the text to keep, and suggest a feedback note. Never say "Saved" unless the file was written.

## After the chat compresses: "RS" (recovery save)
When the chat has been compressed, the next save rebuilds from the real earlier messages (search this chat's history), not from the summary. The owner can trigger it with **"RS"**. After an RS, offer to move to a new chat (below).

## The cleanup commands
- **LE** (Loose Ends): a numbered list of what's still open: for the owner, waiting on others, not yet saved. Changes nothing. Starts with a **TLDR** (what they must do), then **Details**, numbered straight through.
- **HK** (Housekeeping): Loose Ends, plus finish or note anything half-done, the inbox check (below), close browser tabs you opened, the quick update check (below), then report and wait for answers, then save.
- **CE** (Check Email): just the inbox check, any time, without the rest of Housekeeping.
- **WU** (Wrap Up): the short close before stopping: finish or note anything half-done, save if needed, close tabs, a few-line report.

**The inbox check** (HK and CE; skip if the manual names no email label or inbox): search for this project's mail and give three lists, emails lettered under each, one line each (sender | subject | why, with a link): **Can delete** (promos, pitches, expired notices; flag phishing), **Can archive** (receipts, statements, closed threads), **Needs you** (real people waiting, deadlines, action required). **Before writing the Can archive list, pull their email label list** and name the exact label(s) each email gets; plain archive with no label only when no label fits. They answer per email ("2a delete, rest of 3 archive"). Unsure between delete and archive: archive. Nothing deleted or archived before their OK.

## Moving to a new chat ("move chat")
Only after the chat has compressed, or when a very long chat switches topics; at most once a day. Save first, then give a starting prompt in a code block:
```
Continuing <project>. Read claude/manual.md in full first. Files updated <date time>.
First thing: <one action>
Waiting on: <person: item>
Today: <items>
Later: <items>
Rules added this chat: <rules, or "none">
```
Suggest the new chat's name: project short name plus today's date as YYYYMMDD (e.g. "Kitchen 20261108"), and tell them to pin it and unpin the old one.

## Updates ("check for updates")
Runs in any Inception project: at every Housekeeping (quietly), and whenever the owner says **"check for updates"**.
1. **Cheap check first:** read https://raw.githubusercontent.com/MattMartin650/inception-core/main/VERSION.md (a web fetch; no sign-in needed). It lists the latest version of each Core skill. Compare with the version in the header of each installed Core skill (this file says "alpha 0.7"). Skills that didn't change keep their older version number.
2. **Same:** say nothing at Housekeeping; "You're up to date" if they asked.
3. **Newer:** tell them in plain words what changed (the "What's new" part of VERSION.md) and which skills to swap. Give a direct download link for each new ZIP: https://github.com/MattMartin650/inception-core/raw/main/releases/<ZIP name>. Then, in the main window's left sidebar, **Plugins** → **⋯** next to each old skill → Delete → the black **Add** button (top right) → upload the new ZIPs, selecting them all at once. (The Plugins page inside Settings has no Add button.) New skills load in the next new chat.
4. **After they confirm:** in the Inception project, update "Inception version installed" and the change log in `claude/my-changes.md` (elsewhere, ask them to say "updated to <version>" there). If the new version conflicts with one of their own rules, point it out and let them decide.
5. **Can't reach GitHub:** try once more, then use the backup releases folder linked in `claude/my-changes.md` if there is one; otherwise say so in one line and skip. Never guess a version.

## Starting a new module
A **module** is a project that does one specialized thing (the Inception project is the home base, not a module). When a topic will run long, has its own people, money or schedule, or keeps crowding out other work, suggest a new module (honest opinion first; they decide).
1. Name it: a full name and a short name.
2. Write its starting prompt in a code block: its lane (what it owns and doesn't), files to create, privacy rules, and what's already known (people, dates, open items). Its instructions must begin with the line `Part of Inception.`
3. The owner creates the project in Claude, pastes the instructions and the prompt, and names and pins the first chat.
4. Add it to the project list in `claude/my-changes.md` (from another project, give them the line to add in their Inception project).
5. Move the topic's notes to the new project; the old one keeps only a pointer.

## Changelog
- **alpha 0.7 (11/25/2026)**: specialized projects are called "modules"; "Starting a new project" is now "Starting a new module".
- **alpha 0.6 (11/25/2026)**: update check reads the public inception-core repo on GitHub (live, no sign-in) instead of the Drive folder, with direct ZIP download links.
- **alpha 0.5 (11/23/2026)**: inbox check pulls the email label list first and names the exact label for each "Can archive" email; update check notes that unchanged skills keep their old version.
- **alpha 0.4 (11/9/2026)**: update check works in any project and at every Housekeeping, cheaply (versioned ZIP names first, the Handbook only when newer); the home project's manual is `my-changes.md`; manuals stay about two pages; backups reworded for any setup; saving-fails rule; paths made consistent.
- **alpha 0.3 (11/9/2026)**: renamed from `inception-saving`; to-do details, the full inbox check, CE.
- **alpha 0.2 (11/8/2026)**: "check for updates".
- **alpha 0.1 (11/8/2026)**: first version.
