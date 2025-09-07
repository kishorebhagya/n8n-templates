## Templates Index
- IG Media Downloader — Telegram bot that receives Instagram links (posts/reels/stories) in chat and replies with the downloadable media. See `Telegram/README.md`.

## Contributing
1. Create a new folder: `<template-name>/`
2. Add:
   - `<template-name>.json` (exported from n8n)
   - `README.md` (what it does, setup, credentials, inputs/outputs, limits)
   - Optional `assets/`
3. Open a pull request with a brief description and optional screenshots.

## Tips
- Use n8n Credentials, not hardcoded secrets.
- Prefer environment variables for tokens and base URLs.
- For webhooks, ensure public reachability or use n8n Tunnel during development.

## License
MIT