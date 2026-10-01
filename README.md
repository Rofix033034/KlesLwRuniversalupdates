# KlesLwR Universal updates

Public release host for **KlesLwR Universal** (Tauri) Windows installers.

This is separate from classic WPF releases:
- WPF: `Rofix033034/KlesLwRdesktopmacroupdates`
- Universal (this repo): `Rofix033034/KlesLwRuniversalupdates`

## How to publish a build

1. Build Universal: `npm run build` in `KlesLwR_Universal`
2. Upload the NSIS installer from `src-tauri/target/release/bundle/nsis/` as a GitHub Release asset
   - Prefer name like `KlesLwR_1.3.4_x64-setup.exe`
3. In license admin → System → **Universal** tab:
   - Repo: `Rofix033034/KlesLwRuniversalupdates`
   - Asset: your setup exe name
   - **Update Configuration** → **Sync from GitHub**
4. Toggle **Force update** ON only when you want to lock old clients

## Crash / bug logs

Clients POST to `https://api.kleslwr.com/api/v1/crash-reports`.
The crash-reports worker forwards embeds to Discord via secret `DISCORD_CRASH_WEBHOOK_URL`.
Universal reports include `product: "universal"` so they are labeled separately from WPF.
