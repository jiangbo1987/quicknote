# QuickNote - Desktop Floating Quick Notes

[![Version](https://img.shields.io/badge/version-1.2.0-blue.svg)](https://github.com/lilaoban/quicknote)
[![Platform](https://img.shields.io/badge/platform-macOS%20%7C%20Windows-lightgrey.svg)]()
[![License](https://img.shields.io/badge/license-MIT-green.svg)](LICENSE)

A lightweight desktop floating note-taking tool that makes capturing ideas as natural as breathing.

---

## 📸 Screenshots

<!-- Uncomment after adding screenshots
![QuickNote Screenshot](screenshot.png)
-->

---

## ✨ Key Features

- **🎯 Zero Distraction** - Floating icon always on desktop, never blocks your workspace
- **⚡ Zero Delay** - Global shortcut brings up note form within 1 second
- **💾 Draft Protection** - Auto-saves drafts while typing, never lose your work
- **🖱️ Free Dragging** - Drag window anywhere, position persists across panel switches
- **📅 Calendar View** - Browse historical notes by date, quick navigation
- **🔐 Offline Authorization** - HMAC-SHA256 signature verification, no internet required
- **🌍 Cross-Platform** - Supports macOS (Intel/ARM64) and Windows (x64)

---

## 🚀 Quick Start

### macOS

1. Download the `.dmg` installer
2. Double-click to open the DMG file
3. Drag QuickNote into the `Applications` folder
4. Launch the app

> **First Launch**: Right-click the app icon → "Open" → Click "Open" again in the dialog

### Windows

**Installer (Recommended)**:
1. Download `QuickNote Setup 1.2.0.exe`
2. Double-click to run, follow the wizard
3. Launch from desktop shortcut

**Portable Version**:
1. Download `QuickNote-1.2.0-Portable.exe`
2. Place in any directory and run directly

> **SmartScreen Warning**: Click "More info" → "Run anyway"

---

## 📖 User Guide

### Record Your First Note

1. **Click** the floating icon (blue circle in bottom-right corner)
2. Enter title (optional) and content
3. Click the "Save" button

### View Notes

- **Today's Notes**: Right-click tray icon → "📋 View Today's Notes"
- **History Notes**: **Double-click** floating icon or right-click tray → "📅 View History"

### Edit & Delete

In the note list, each note has action buttons:
- ✏️ **Edit** - Modify title or content, then save
- 🗑️ **Delete** - Delete note (irreversible, please be careful)

### Drag Window

- Hold the **title bar** at the top of the window to drag and move
- When switching panels (Today's Notes ↔ History ↔ Settings), window position **won't reset**
- When invoked via global shortcut, window repositions near cursor

> **Note**: Only the title bar area is draggable; input fields, buttons, and other elements remain interactive.

---

## ⌨️ Keyboard Shortcuts

| Shortcut | Platform | Function |
|---------|----------|----------|
| `Cmd + Shift + N` | macOS | Show note form at cursor position |
| `Ctrl + Shift + N` | Windows | Show note form at cursor position |

### Customize Shortcuts

1. Right-click tray icon → "⚙️ Settings"
2. Find the "Shortcut" setting
3. Click the **Record** button
4. Press your desired key combination
5. Save settings

---

## 🔑 Authorization

| Version | License Prefix | Price | Note Limit |
|---------|---------------|-------|-----------|
| Free | — | Free | 1,000 notes |
| Annual | `QNPRA-` | ¥9.9/year | Unlimited |
| Lifetime | `QNPRO-` | ¥49 (one-time) | Unlimited |

### Activation Steps

1. Right-click tray icon → "⚙️ Settings"
2. Go to "Authorization Info" page
3. Enter license key
4. Click "Activate" button

> Free version requires no activation, ready to use after installation.

---

## 📂 Configuration File Locations

| Platform | Config Path |
|----------|-------------|
| macOS | `~/Library/Application Support/QuickNote/` |
| Windows | `%APPDATA%\QuickNote\` |

**Important Files**:
- `license.json` - Authorization info (with HMAC signature)
- `settings.json` - User settings (shortcuts, save directory, etc.)
- `notes/` - Note files directory (organized by date)

---

## 🛠️ Developer Guide

### Requirements

- Node.js >= 18.0.0
- npm >= 9.0.0
- Python 3 (for generating license keys)

### Install Dependencies

```bash
cd /Users/lilaoban/workspace/quicknote
npm install
```

### Development Mode

```bash
npm start
```

### Build

```bash
# macOS (Intel + ARM64)
npm run build-mac
npm run build-mac-arm

# Windows (x64)
npm run build-win

# All platforms
npm run build-all
```

Build artifacts are located in the `dist/` directory.

---

## 🐛 Troubleshooting

### macOS shows "Cannot verify developer"

**Solution**:
1. Right-click the QuickNote icon
2. Select "Open"
3. Click "Open" in the dialog

### Windows shows SmartScreen warning

**Solution**:
1. Click "More info"
2. Click "Run anyway"

### Shortcut not working

**Possible causes**:
1. Shortcut conflict with other apps → Change shortcut in settings
2. macOS hasn't granted accessibility permissions → System Settings → Privacy & Security → Accessibility, add QuickNote
3. Windows not running as administrator → Right-click icon → "Run as administrator"

### How to backup notes?

Notes are stored locally as JSON files:
- macOS: `~/Library/Application Support/QuickNote/notes/`
- Windows: `%APPDATA%\QuickNote\notes\`

Simply copy the entire `notes/` directory to backup.

---

## 📄 Documentation

- **Product Requirements Document (PRD)**: [PRD_QuickNote.md](PRD_QuickNote.md)
- **User Manual**: [使用手册.md](使用手册.md) (Chinese)
- **License Management**: [管理运维_授权码.md](管理运维_授权码.md) (Chinese)

---

## 🤝 Contributing

Issues and Pull Requests are welcome!

1. Fork this repository
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

---

## 📝 Changelog

### v1.2.0 (2026-06-01)

**New Features**:
- ✅ Window drag position persistence (no reset on panel switch)
- ✅ Windows frameless window drag support
- ✅ Real-time authorization status bar
- ✅ HMAC signature for license.json (tamper-proof)
- ✅ Custom validity period support with `--days` parameter

**Fixes**:
- Fixed authorization verification stuck on "Verifying"
- Fixed window position reset on panel switch
- Fixed draft save failure issue

### v1.1.0 (2026-05-22)

**New Features**:
- Note editing and deletion
- Settings panel
- WeChat public account QR code

### v1.0.0 (2026-05-20)

**Initial Release**:
- Basic CRUD functionality
- Floating icon interaction
- Global shortcuts
- Calendar view
- Authorization system

---

## 📄 License

MIT License - See [LICENSE](LICENSE) file for details.

---

## 🙏 Acknowledgments

- [Electron](https://www.electronjs.org/) - Cross-platform desktop app framework
- [electron-builder](https://www.electron.build/) - Build tool

---

## 📧 Contact

- Project Homepage: https://quicknote.app
- GitHub Issues: https://github.com/lilaoban/quicknote/issues
- Email: [TBD]

---

**Never let inspiration slip away** 💡