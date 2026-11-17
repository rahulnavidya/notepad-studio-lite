# Storage and Privacy

Notepad Studio Lite is a client-side application. The Pass 3 source does not require an account, project backend, or remote document service.

## What is stored

The application saves its workspace in the current browser's `localStorage`. The workspace includes document text and names, active-document information, editor settings, custom themes, favourites, recent appearance history, recent documents, and saved presets.

Autosave is scheduled shortly after edits. The application reports when storage is unavailable or a save fails; in that situation, the current text remains in memory for the active page session. Export a copy or back up the workspace rather than assuming the browser has saved it.

## What is not persisted

File-system handles are deliberately kept outside the serializable workspace state. They are not written to `localStorage` or included in workspace backups. This means file associations do not survive a page reload. Documents may be restored from browser storage, but the associated computer file must be opened or selected again.

## Workspace backups

Use **Back up workspace** to download a JSON file containing documents and workspace settings. Backups are portable files and can be stored separately from the browser.

Use **Restore backup** to load a previously created backup. The app validates the backup before applying it. Restore is a workspace replacement operation, so save a new backup of the current workspace first if you need it.

## Practical safety checklist

1. Back up important work regularly.
2. Keep backup files outside the browser profile.
3. Before clearing browser data or changing profiles, export the workspace.
4. Do not rely on a linked file handle surviving a reload.
5. Store sensitive text only in a device and browser profile you trust.

## Limits

- Browser storage can be cleared, quota-limited, blocked, or unavailable.
- Private/incognito sessions may have different storage lifetime and quota behaviour.
- Browser file permissions are governed by the browser and operating system.
- The application does not promise encryption of local browser storage or downloaded backups.

This document describes the application's storage design, not a guarantee that every browser handles storage and permissions identically.
