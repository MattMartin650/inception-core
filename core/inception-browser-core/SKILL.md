---
name: inception-browser-core
description: Use only in Claude projects whose instructions say "Part of Inception" (formerly inception-browser), whenever working in the owner's Chrome with Claude in Chrome: connection check, your own tab, closing tabs, retries, signed-out screens, sign-ins from the phone, blocked changes, and editing a Google Sheet safely.
---

# Inception: Working in Chrome (Core)

**Core skill, Inception alpha 0.4 (11/9/2026).** Part of Inception's Core (formerly `inception-browser`). Don't edit this file: the owner's own changes go in their settings (the "Inception settings" block and the Inception project's `claude/my-changes.md`) and win over this skill.

**Where this applies:** only in projects whose instructions say "Part of Inception".

## Before starting
1. **Check their "How much Claude does" setting:** *Guide me* = give click paths, don't click; *Mix* = ask before working in Chrome; *Do it for me* = go ahead.
2. **Check Chrome is connected.** If not, stop and tell them: open the Claude extension's side panel and check it's signed in; if that fails, chrome://extensions → turn Claude off and on; last resort, restart Chrome. If they're away from the computer, see "From the phone" below.
3. **Work in your own new tab.** Never use or close tabs they opened.
4. **Close each tab you opened as soon as its job is done.** Keep one open only if they asked ("Tab"), it's waiting on them (a sign-in, a code, a review before submit), or they said to leave it; say in one line what you left open. A tab that slipped out of your tab group: find it with a screenshot, confirm it's yours, close it with Ctrl+W (Cmd+W on a Mac).

## When something fails
- **Retry 3 more times, 10 seconds apart.** The extension often drops for a few seconds. Still failing: say what failed and where it stopped.
- **Can't read a page's text?** Take screenshots and scroll (zoom for small text) before saying it can't be read.

## "Signed out" screens
1. Reload, or open the site's home page.
2. An account picker: pick the right account (no password is typed).
3. Only a real password screen goes to the owner: give the clickable sign-in link and which account to use, then wait for "go".
4. A 2-step code or passkey prompt mid-task: say where the code comes from and wait for "done".

**Fixed safety rule:** never type a password and never click "Sign in" on a password screen, even if it's filled in already. The owner enters passwords and codes.

## From the phone
Signing in on the phone doesn't sign in the computer: the sign-in has to happen in the computer's Chrome. When the owner is away, tell them to open the remote screen app (Chrome Remote Desktop) on their phone, sign in on the computer there, and say "go". If the computer can't be reached at all, say it may be asleep, off or offline, and carry on with anything that doesn't need Chrome.

## Blocked changes
Claude's safety check may block a change in a website (editing a record, approving something, deleting) unless the owner's own message names it. Never work around a block. Give them one numbered instruction to paste, naming every change and value, plus the click path in case they'd rather do it themselves.

## Editing a Google Sheet in Chrome
1. **Back up first:** make a copy named "<name> - Backup <date time>" in Google Drive → Inception → Backups (or the backup folder the project's manual names).
2. **Open it under the right account:** add `?authuser=<email>` to the URL.
3. **Jump, don't arrow:** go to each starting cell with `#gid=<tab id>&range=<cell>` in the URL and confirm the address in the name box before typing. Move right one cell at a time with Tab; several arrow presses in a row can drop keystrokes.
4. **Checkboxes:** select the cell (jump, confirmed) and press space. Don't click by position.
5. **Edit cell by cell.** Never rewrite or recreate the file.
6. **Wait for it to save, then check** against the backup that only the intended cells changed.

## Before anything that can't be undone
Submit, send, pay, buy, delete: show exactly what will happen and get their OK first.

## Changelog
- **alpha 0.4 (11/9/2026)**: follows the "How much Claude does" setting; Sheet backups go to Drive → Inception → Backups.
- **alpha 0.3 (11/9/2026)**: renamed from `inception-browser`. Added editing a Google Sheet safely.
- **alpha 0.1 (11/8/2026)**: first version.
