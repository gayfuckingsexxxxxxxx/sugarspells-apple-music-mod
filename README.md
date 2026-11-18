# sugarspells'🍎🎵

An open source Android player for Apple Music, built with Kotlin, Jetpack Compose and Material 3.
It plays music through **your own official Apple Music account** - no piracy, no illegal downloads.

> Not affiliated with or endorsed by Apple Inc. Apple Music and MusicKit are trademarks of Apple Inc.

## Planned features (see modes below)
- Player: play/pause, next/previous, queue, library, search, playlists
- Motion artwork when the API offers it, static cover fallback otherwise
- Word-by-word synced lyrics (degrades to line sync)
- Apple Music-style typography (Inter, open license)
- iPadOS-inspired liquid glass UI, adaptive layout (sidebar on tablets, bottom bar on phones), light/dark theme

## Two playback modes
| Mode | Cost | What works |
|------|------|-----------|
| **Session mode** (default) | Free | Shows and controls what the official Apple Music app is playing (cover, progress, play/pause/next/previous), Apple TV-style animated player, synced lyrics from LRCLIB |
| **MusicKit mode** (planned) | Apple Developer Program (99 USD/year) | Catalog, library, search, playlists, motion artwork, word-synced lyrics |

Session mode needs no developer account or API keys: playback, DRM and your account stay inside Apple's own app.
Catalog, search and motion artwork come from the Apple Music API, which requires a paid developer token,
so those arrive with MusicKit mode (contributors with a membership welcome).

## Lyrics
Lyrics come from [LRCLIB](https://lrclib.net), a free, open, keyless database of time-synced lyrics. Timing is per line;
the word-by-word highlight is **estimated** from the line timing unless a record includes real word tags (those are used automatically).
Providers are pluggable (`LyricsProvider`). Musixmatch is not bundled: its official free plan returns only a 30% preview, and synced
lyrics need a paid commercial plan; unofficial access through keys extracted from its app breaks its terms and is not supported here.

## Requirements (session mode)
- Android 8.0+, internet (for lyrics) and the official Apple Music app, signed in with an active subscription
- Notification access enabled for sugarspells (the app guides you)

## Privacy
Android only lets an app read another app's media session if it holds notification access. sugarspells uses it **only** to read the
`com.apple.android.music` media session. It never reads, stores or sends notification content, The only network request is the lyrics lookup, which sends the song title, artist, album and duration to LRCLIB.

## Build
1. Open in Android Studio, or run `gradle wrapper` once and then `./gradlew assembleDebug`.
2. For MusicKit mode (later): copy `local.properties.example` to `local.properties` and add your keys; download Apple's
   MusicKit for Android SDK into `app/libs/` (proprietary, git-ignored, never commit it).

## Status
See [CHANGELOG.md](CHANGELOG.md) and the milestones in Issues.

## License
[MIT](LICENSE) - applies to this project's code only, not to Apple's SDK or content.
