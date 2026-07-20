# Snapdrop - Public

Snapdrop is a local-first desktop photo library app for organizing, browsing, and searching your photos.It has been developed with security and privacy first mindset to allow all processing within your desktop so no data leaves your machine. 
This repository is the public release repository. It is intended for end users who want to download and run Snapdrop.

<img width="1510" height="848" alt="Screenshot 2026-07-19 at 7 20 44 PM" src="https://github.com/user-attachments/assets/c76b0e1f-ac43-404c-b890-237cb9af6ee4" />

## Highlights

- Local-first photo management (your files stay on your machine)
- Fast gallery browsing with thumbnails and keyboard navigation
- EXIF metadata viewer (camera, date, lens, GPS when available)
- Collections, favorites, tags, duplicate detection, and trash workflow
- Optional local AI features for face detection and semantic photo search

## Platform Compatibility

- macOS 11.0 (Big Sur) or newer
- Current release builds: Apple Silicon (arm64)

If your macOS version is below the minimum requirement, the app may fail to install or launch.

## Install

1. Open the Releases page in this repository.
2. Download the latest `.dmg` for macOS.
3. Open the DMG and drag Snapdrop to Applications.
4. Launch Snapdrop from Applications.

## Optional AI Features

Snapdrop works without AI, but you can optionally enable:

- Face detection and grouping
- CLIP-based semantic search
- AI-assisted auto-tagging

AI setup is guided in-app.

1. Open `Settings` -> `AI Provider` -> `AI Setup Status`.
2. Check readiness for face models, Python runtime, and packages.
3. Use the displayed model install folder path to place required model files.
4. Click `Re-check AI Setup`.

If AI dependencies are missing, AI actions are disabled gracefully and Snapdrop continues to work for non-AI features.

## Keyboard Shortcuts

- Arrow keys: navigate photos
- Enter: open viewer
- Space: toggle selection
- F: toggle favorite
- Cmd/Ctrl + A: select all
- Delete/Backspace: move selected to trash
- ?: show shortcuts help

## Troubleshooting

### macOS says the app is damaged or cannot be opened

This is usually a Gatekeeper/quarantine issue for unsigned or non-notarized builds.

Run one of the following commands depending on where the app is:

- Installed app:

```bash
xattr -dr com.apple.quarantine "/Applications/Snapdrop.app"
```

- Downloaded DMG:

```bash
xattr -dr com.apple.quarantine "$HOME/Downloads/Snapdrop_0.1.0_aarch64.dmg"
```

Then verify Gatekeeper status:

```bash
spctl -a -vv "/Applications/Snapdrop.app"
```

### AI features are disabled

- Open `Settings` -> `AI Provider` -> `AI Setup Status`
- Install missing dependencies shown in that panel
- Place required ONNX files in the exact folder shown by the app
- Click `Re-check AI Setup`

## Privacy

- Snapdrop is designed to run locally.
- Photo indexing data stays on your machine.
- AI processing in current builds runs locally using local runtime components.

## Upcoming
- mcp server so you can query you images from agents in natural language
- support for X86 and Windows
- Supporting more models

## License

Add your project license here (for example, MIT).

