# Gemlock

A small Windows tool for switching between Riot accounts with one click.

**[Download the latest Gemlock.exe](https://github.com/YalinFrncgllr/Gemlock-releases/releases/latest/download/Gemlock.exe)** — or see [Releases](https://github.com/YalinFrncgllr/Gemlock-releases/releases). No Python needed.

This repository only hosts Gemlock's releases and update information. The source code is private.

## What it does
- Pick a game (Valorant, League of Legends, TFT, or just the Riot Client) and an account; Gemlock types the login into the Riot Client and launches the game.
- Shows Valorant ranks (through the Gemlock rank server, no API key needed) and League Solo/Duo, Flex and TFT ranks (read from the local League client after you log in), with rank emblems.
- English and Turkish interface.
- Optionally opens Blitz together with League.
- Optional League pick screen helper (Settings → League pick screen): suggests champions for your role from the enemy picks you can see and, in bot lane, your lane partner's pick; in blind pick it weighs meta and matchup safety. It also suggests picks for your lane partner and can accept found matches automatically. Suggestions appear in a strip docked to the League client. When it is on, Gemlock stays open in the background between games: during a match it only waits (it does not touch the game or the client), and it closes when the League client closes. It only reads what the League client already shows in champion select.

## Install
1. Download **[Gemlock.exe](https://github.com/YalinFrncgllr/Gemlock-releases/releases/latest/download/Gemlock.exe)** and double-click it.
2. Windows may show "Windows protected your PC" because the exe is not code-signed. Click **More info → Run anyway**.
3. Gemlock installs itself to `%LOCALAPPDATA%\Gemlock`, removes the downloaded file and puts a **Gemlock** shortcut on your desktop.
4. Add your accounts with **+ Add account**. Everything you add stays encrypted on your own PC.

Each release lists the exe's SHA-256 (`Gemlock.exe.sha256`), so you can check that your download is intact.

## Privacy and security
- Everything stays local: account labels, usernames, passwords, Riot IDs, ranks and settings live only on your PC in `%LOCALAPPDATA%\Gemlock\data`, encrypted with Windows DPAPI. Only your Windows user on your PC can decrypt them.
- Gemlock never uploads your data. Its only network requests are: Riot IDs (public) to the Gemlock rank server (hosted on Vercel; it asks the HenrikDev API, caches results and stores nothing) for Valorant ranks; champion IDs to the same server for pick suggestions (only if you turn them on); and reading `version.json` and new versions of `Gemlock.exe` from this repository for updates.
- Credentials are typed only while the Riot Client window has focus; if focus changes, typing pauses.
- Rank emblems are downloaded once to your PC from community asset mirrors (valorant-api.com, CommunityDragon).

## Updates
Gemlock checks `version.json` in this repository on startup and updates itself after you confirm. The new exe is downloaded from this repository's Releases and checked against the SHA-256 in `version.json` before it is installed.

## Legal
Copyright © 2026 YalinFrncgllr. All rights reserved. You may download and use Gemlock for free; you may not copy, modify, redistribute or sell it, or reuse its code, without permission.

Gemlock was created under Riot Games' "Legal Jibber Jabber" policy using assets owned by Riot Games. Riot Games does not endorse or sponsor this project.
