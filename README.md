# Gemlock

A small Windows tool for switching between Riot accounts with one click.

**[Download Gemlock-Setup.exe](https://github.com/YalinFrncgllr/Gemlock-releases/releases/latest/download/Gemlock-Setup.exe)** — or see [Releases](https://github.com/YalinFrncgllr/Gemlock-releases/releases). No Python needed.

This repository only hosts Gemlock's releases and update information. The source code is private.

## What it does
- Pick a game (Valorant, League of Legends, TFT, or just the Riot Client) and an account; Gemlock types the login into the Riot Client and launches the game.
- Shows Valorant ranks (through the Gemlock rank server, no API key needed) and League Solo/Duo, Flex and TFT ranks (read from the local League client after you log in), with rank emblems.
- English and Turkish interface.
- Optionally opens Blitz together with League.
- Optional League pick screen helper (Settings → League pick screen): suggests champions for your role from the enemy picks you can see and, in bot lane, your lane partner's pick; in blind pick it weighs meta and matchup safety. It also suggests picks for your lane partner and can accept found matches automatically. Suggestions appear in a strip docked to the League client. By default Gemlock closes completely when a match starts, so it never runs during a match (open it again for the next game). If you turn off "Close Gemlock when a match starts", it sleeps during matches instead (it does not touch the game or the client, it only checks the list of running programs) and is ready for back-to-back games, remakes included. It only reads what the League client already shows in champion select.

## Install
1. Download **[Gemlock-Setup.exe](https://github.com/YalinFrncgllr/Gemlock-releases/releases/latest/download/Gemlock-Setup.exe)** and run it.
2. Windows may show "Windows protected your PC" because the installer is not code-signed. Click **More info → Run anyway**.
3. The installer puts Gemlock in `%LOCALAPPDATA%\Gemlock` (no administrator rights needed) and adds Desktop and Start menu shortcuts. You can uninstall it from Windows Settings → Apps like any other program; it asks whether to keep your accounts.
4. Add your accounts with **+ Add account**. Everything you add stays encrypted on your own PC.

Each release lists the SHA-256 of its files (`*.sha256`), so you can check that your download is intact.

## Privacy and security
- Everything stays local: account labels, usernames, passwords, Riot IDs, ranks and settings live only on your PC in `%LOCALAPPDATA%\Gemlock\data`, encrypted with Windows DPAPI. Only your Windows user on your PC can decrypt them.
- Gemlock never uploads your data. Its only network requests are: Riot IDs (public) to the Gemlock rank server (hosted on Vercel; it asks the HenrikDev API, caches results and stores nothing) for Valorant ranks; champion IDs to the same server for pick suggestions (only if you turn them on); and reading `version.json` and new versions of `Gemlock.exe` from this repository for updates.
- Credentials are typed only while the Riot Client window has focus; if focus changes, typing pauses.
- Rank emblems are downloaded once to your PC from community asset mirrors (valorant-api.com, CommunityDragon).

## Updates
Gemlock checks `version.json` in this repository on startup and updates itself after you confirm. The new `Gemlock.exe` is downloaded from this repository's Releases and checked against the SHA-256 in `version.json` before it is installed.

## Legal
Copyright © 2026 YalinFrncgllr. All rights reserved. You may download and use Gemlock for free; you may not copy, modify, redistribute or sell it, or reuse its code, without permission.

Gemlock was created under Riot Games' "Legal Jibber Jabber" policy using assets owned by Riot Games. Riot Games does not endorse or sponsor this project.
