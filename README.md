# Tonariyuki

A macOS app that sits quietly beside your online conversations — live on-device transcription with gentle, opt-in AI conversation support. Not a meeting recorder; it's a tool that helps you connect with people you don't know well yet.

- **On-device transcription** — your voice (mic) and the other person's voice (system audio) are transcribed locally. No audio ever leaves your Mac.
- **AI support is opt-in** — when enabled, only text is sent to the AI provider of your choice. Never audio.
- **Conversation tools** — pre-call briefings, in-call topic suggestions, and per-person notes.

## Requirements

- macOS 26 (Tahoe) or later, Apple Silicon
- Earphones / headphones recommended
- Transcription supports **Japanese (ja-JP) only**

## Install

1. Download the latest `.dmg` from [Releases](https://github.com/akifo/tonariyuki-releases/releases)
2. Open it and drag **Tonariyuki.app** into **Applications**

### First launch

The app is not notarized yet, so macOS blocks it once. Allow it via System Settings:

1. Double-click Tonariyuki.app, then dismiss the "can't be opened" dialog
2. Open **System Settings → Privacy & Security**, scroll down to the blocked-app message
3. Click **"Open Anyway"** and authenticate

This is needed only once. On first session, grant **Microphone** and **System Audio Recording** permissions when prompted (the speech model downloads automatically on first use).

## Updates

The app checks for updates on launch and updates itself in one click.

## Feedback

Please use [Issues](https://github.com/akifo/tonariyuki-releases/issues).
