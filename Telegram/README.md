# IG Media Downloader — Telegram Bot

A Telegram bot that lets users send an Instagram link (post/reel/stories) and receive the downloadable media file back.

## What It Does
- Listens for Telegram messages.
- Detects Instagram URLs in the message.
- Resolves the direct media URL(s) for the post/reel/stories.
- Downloads and sends media back to the user via Telegram.

## Files
- `IG Media Downloader.json` — n8n workflow export

## Prerequisites
- n8n v1.0+ (self-hosted or Cloud)
- Telegram Bot token (via BotFather)

## Import
- n8n → Workflows → Import from File → select `IG Media Downloader.json`
- Or copy the JSON and use Import from Clipboard

## Setup
1. Create a Telegram bot:
   - In Telegram, search for BotFather → `/newbot` → get the bot token.
2. In n8n, open the workflow and configure:
   - Telegram node credentials with your bot token.
   - (Optional) Allowed chat IDs if you want to restrict usage.
   - (Optional) Storage node credentials and destination path if saving files.
3. Activate the workflow.
4. Start a chat with your bot and send an Instagram link.

## Environment Variables
- [YOUR_X_IG_APP_ID]
- [YOUR_IG_COOKIE]

## Usage
- Send a message containing a public Instagram post/reel URL, e.g.:
  - `https://www.instagram.com/p/<id>/`
  - `https://www.instagram.com/reel/<id>/`
  - `https://www.instagram.com/<username>/`
  - `https://www.instagram.com/stories/<username>/`
- The bot replies with the media file. For carousels, it may send multiple files.

## Inputs
- Telegram message text with at least one Instagram URL.

## Outputs
- Telegram media message(s) sent back to the user.

## Notes & Limitations
- Only public content is supported without authenticated flows.
- Instagram can change endpoints; headers/logic may need tuning over time.
- Large videos may require higher timeouts.
- Rate limits may apply; consider throttling for high-volume usage.

## Troubleshooting
- Bot not responding: verify the workflow is active and bot token is valid.
- 403/429 errors: slow requests, add realistic headers, or retry with backoff.
- No media returned: confirm the URL is public and accessible.

## License
MIT