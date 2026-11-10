# Jump to Ping for Valenced

Find unread pings in one place and jump to their messages. Version: **1.0.0-beta**.

## Features

- **Profile bar button** beside the notifications bell, using the original Jump to Ping design.
- **Unread ping list** for up to 50 chats, with channel/server or DM names, author, message preview, time and unread count.
- **Jump to a message** by tapping a row or its **Jump to** button. Hold the profile bar button to jump directly to the newest listed chat's first unread ping.
- **Resolve uncached pings** from recent channel messages. If an exact match cannot be found, open the oldest unread message instead.
- **Count badge** with a `99+` cap, and an option to keep the button visible when there are no pings.
- **Optional DMs** alongside mentions and replies. The list follows Discord's unread counters.
- **Light and dark themes**, with the existing settings cards and quick guide preserved.

## Installation

In Valenced, open **Plugins → Advanced → Repository URL** and add:

```text
https://raw.githubusercontent.com/dariussbezy/Jump-To-Ping/refs/heads/main/JTP/index.json
```

Select the **beta** channel, install **Jump to Ping**, enable it and restart Discord. Open the plugin settings to configure **Only show with pings**, **Show count badge** and **Include DMs**.

## Privacy

The plugin uses Discord's unread counters and message cache. When resolving an uncached ping, it requests recent messages through Discord's own API, using your existing session. Nothing is sent to an external service.

Only the three preferences are saved locally. Message previews remain in memory and are cleared when the plugin stops. No token or API key needs to be entered.

## Repository structure

Sources use the [official Valenced plugin template](https://github.com/Valenced/valenced-plugin-template/tree/9a4f9187137a75d86fe552d0e594889a6e6fd7e5). The implementation is in [`plugins/JTP/js`](plugins/JTP/js), with shared configuration and the official plugin CLI at the repository root. `./gradlew packageAllPlugins` packages the plugin; `npm run publish:local` prepares the pool and both repository indexes. The `JTP/index.json` installation URL remains supported. Artifacts stay on `main` and the beta channel.

Install development dependencies with `bun install --frozen-lockfile` before running the root scripts. The compiler and SDK revisions are pinned in `package.json`.
