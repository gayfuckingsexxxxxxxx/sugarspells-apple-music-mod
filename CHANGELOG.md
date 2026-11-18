# Changelog

All notable changes to this project are documented here.
Format based on [Keep a Changelog](https://keepachangelog.com/).

## [Unreleased]

### Added
- Apple TV-style player: cover on the left and lyrics on the right on tablets/landscape; compact layout on phones
- Animated backdrop with colours extracted from the cover, cover cross-fade and bounce on pause/play
- Synced lyrics from LRCLIB with an animated active line and word-by-word highlight (estimated unless the source provides word tags); tap a line to seek
- LRC parser with enhanced word tags, `LyricsProvider` interface and in-memory cache, with unit tests
- Phase 1 (free): `PlaybackEngine` interface and `AppleMusicSessionEngine`, which reads and controls the official Apple Music app via its media session
- Now playing screen (cover, title, artist, progress, previous/play-pause/next) and notification-access onboarding
- English and Spanish strings
- Project scaffold: Gradle (Kotlin DSL), Compose, Material 3, light/dark theme
- Launcher icon (adaptive + legacy) and app name
- CI workflow (build + lint) and GitHub bootstrap script for milestones and issues
- MIT license, README, CONTRIBUTING

### Changed
- INTERNET permission is back, used only for the lyrics lookup
