# Technical Notes

## Distribution model

Notepad Studio Lite Pass 3 is distributed as a single HTML document. Its styles and application logic are embedded in that file. There is no package manager setup, transpilation step, bundler, server process, or third-party runtime dependency.

The repository's intended entry point is `index.html`.

## High-level structure

The HTML file contains:

1. Document metadata and responsive viewport configuration.
2. An embedded CSS design system and responsive application layout.
3. The editor interface, document tabs, sidebar panes, dialogs, search UI, status bar, and overlays.
4. One self-invoking JavaScript application module.

The JavaScript module manages the current workspace, documents, editor preferences, appearance data, persistence, search, imports/exports, and file operations.

## Persistence layers

### Workspace state

The serializable workspace is stored in `localStorage`. File-system handles are intentionally excluded because they are not serializable and should not be included in workspace backups.

### File associations

Pass 3 keeps file associations in session memory, keyed by document ID. These associations track the file handle, display name, extension, last save time, metadata, dirty state, and workflow status.

### Workspace backup

The JSON backup includes the app identifier, backup kind, version, timestamp, documents, active document, settings, themes, favourites, recents, recent documents, and presets. Pass 3 writes backup version 2 and accepts versions 1 and 2 for restore.

## File APIs and fallback behaviour

- The File System Access API is used where the browser exposes `showOpenFilePicker` and `showSaveFilePicker`.
- File handles use `createWritable()` for writes.
- Permission checks/requests are performed as part of the user-initiated save workflow.
- The app retains fallback import and download paths using the browser's file input, FileReader, Blob, and object URL APIs.

The supported experience is therefore capability-based, not identical across all browsers.

## Resource limits in the application

- Individual text file open/import size: 8 MiB.
- Workspace backup validation accepts up to 200 documents.
- Workspace backup restore rejects files larger than 32 MiB.

These are application-level limits in the Pass 3 source, not browser-wide limits.

## Editing and release discipline

The reviewed Pass 3 artifact is frozen. A code change should be treated as a new version, not silently folded into the frozen release. Keep changes scoped, preserve the single-file distribution, and rerun the relevant browser and regression checks before publishing a changed application file.
