# Notepad Studio Lite

A zero-dependency, browser-based plain-text editor focused on a comfortable writing workspace, customizable appearance, multi-document workflows, and local file handling.

**Current release:** Pass 3  
**Format:** Single self-contained HTML file  
**Runtime dependencies:** None

## Features

- **Plain-text editing:** text stays literal. The editor does not render Markdown, HTML, or rich-text formatting.
- **Multiple documents:** create, rename, duplicate, switch between, and close documents.
- **Find and replace:** search within the current document, with match-case and whole-word options.
- **Workspace-wide search:** search across open documents.
- **Appearance customization:** 41 design languages, 40 built-in colour themes, custom themes, saved appearance presets, favourites, and recent selections.
- **Editor preferences:** font family and size, line spacing, tab width, line numbers, word wrap, and browser spellcheck.
- **File workflow:** open text files, save to a linked file, Save As, import text, and export a separate copy.
- **Workspace backup:** export documents and settings to a JSON backup and restore a backup later.
- **Command palette:** access common actions from the keyboard.
- **Responsive interface:** includes a compact layout for smaller screens.

The app is distributed as one HTML file containing its own CSS and JavaScript. There is no build step, package installation, backend, or network service required to run the editor.

## Quick start

1. Download `index.html` from this repository.
2. Open it in a modern desktop browser.
3. Start typing, or use **New** to create another document.
4. Use **Open…** to load a local text file.
5. Use **Save**, **Save As…**, or **Export Copy** depending on how you want to save your work.

For the best file workflow, use a browser that supports the File System Access API. Other browsers can use the app's file-picker and download fallbacks where supported.

## Data and privacy

Notepad Studio Lite is a client-side application. It does not require an account or send documents to a project server.

- The app autosaves its workspace in the current browser's local storage.
- Documents stored in browser storage are tied to that browser profile and origin.
- File-system handles used by **Open** and **Save** are session-only. After a reload, documents are restored from browser storage, but you must open or associate the files again.
- Clearing browser site data, using private browsing, or switching browsers/profiles can make locally stored work unavailable.
- Use **Back up workspace** regularly to export a portable JSON backup.
- Opening, saving, and exporting files involves the file or download actions you explicitly initiate in your browser.

**Important:** browser storage is not a substitute for a proper backup. Keep copies of important work somewhere safe.

## Keyboard shortcuts

| Shortcut | Action |
|---|---|
| Ctrl+Alt+N | New document |
| Ctrl+O | Open file |
| Ctrl+S | Save to the linked file |
| Ctrl+Shift+S | Save As |
| Ctrl+F | Find and replace |
| F3 / Shift+F3 | Next / previous search match |
| Ctrl+Shift+F | Search all documents |
| Ctrl+G | Go to line |
| Ctrl+Alt+D | Duplicate document |
| F2 | Rename document |
| Alt+W | Close document |
| Ctrl+Alt+1–9 | Switch to tab |
| Alt+Shift+← / → | Move current tab |
| Tab / Shift+Tab | Indent / outdent the current line |
| Ctrl+Shift+P | Open command palette |
| Esc | Close search, dialog, or drawer |

These are the shortcuts displayed by the app. Browser and operating-system shortcut handling can vary.

## File operations

- **Open:** opens a text file as a document in the editor.
- **Save:** writes changes to the file currently linked to the document.
- **Save As:** associates the document with a selected file destination.
- **Export Copy:** downloads a separate text copy and does not replace the linked file.
- **Import:** loads text content into the workspace.
- **Back up workspace:** downloads a JSON file containing the workspace data and settings.
- **Restore backup:** restores workspace data from a previously created JSON backup. Treat restore as a replacement operation and keep a separate backup before using it.

The native open/import workflow accepts common text-oriented formats including TXT, TEXT, MD, MARKDOWN, LOG, JSON, and CSV. Individual text files are limited to 8 MiB by the app.

The File System Access API is used where available. Browser support and permission rules vary, so file operations may use conventional file-picker and download fallbacks instead.

## Browser compatibility

Use a current version of a major browser (Chromium-based browsers, Firefox, or Safari). The exact file-saving experience depends on browser support:

- Browsers supporting the File System Access API can provide linked-file workflows, subject to user permission.
- Other browsers rely on supported file input and download mechanisms.
- Browser storage is scoped to the browser profile and site origin.
- Native operating-system permission prompts and file dialogs are controlled by the browser and operating system, not by this app.

This project does not claim identical native file-system behaviour across every browser or operating system.

## Documentation

- [User Guide](docs/USER-GUIDE.md): editing, documents, search, themes, files, and backups.
- [Keyboard Shortcuts](docs/KEYBOARD-SHORTCUTS.md): shortcut reference.
- [Storage and Privacy](docs/STORAGE-AND-PRIVACY.md): where data lives and how to protect it.
- [Technical Notes](docs/TECHNICAL-NOTES.md): single-file architecture and browser APIs.
- [Quality Assurance](docs/QUALITY-ASSURANCE.md): recorded Pass 3 verification scope and limitations.
- [Changelog](CHANGELOG.md): release notes.
- [License](LICENSE): MIT License.

## Project status

Pass 3 is the reviewed and frozen release represented by the committed `index.html`. The application file is kept self-contained. Documentation may be clarified independently, but changes to application code should be treated as a new version and verified before release.

## Contributing

Bug reports and focused improvements are welcome. Please include:

- Browser and operating-system versions.
- Steps to reproduce the issue.
- Expected and actual behaviour.
- Whether the issue affects editing, browser storage, or a particular file workflow.

For proposed code changes, preserve the single-file distribution unless the project explicitly adopts a different structure. Do not remove or weaken existing QA assertions merely to make a test pass.

## License

This project is licensed under the MIT License. See [LICENSE](LICENSE).
