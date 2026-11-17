# User Guide

This guide describes the Pass 3 interface and workflows in Notepad Studio Lite.

## 1. The editing workspace

The main editor is a plain-text writing surface. It stores the characters you type as text; it does not render Markdown, HTML, or rich-text formatting.

The interface is arranged around:

- **Title bar:** app identity, current document title, and command palette.
- **Document tab bar:** open documents and the new-document control.
- **Toolbar:** common document, file, search, and text-size actions.
- **Editor:** the active document's text.
- **Status bar:** document name, workspace save state, linked-file state, cursor position, and text counts.
- **Sidebar:** Appearance, Editor, Document, Workspace, Shortcuts, and About sections.

On smaller screens the sidebar and controls use a more compact layout.

## 2. Working with documents

### Create and switch

Choose **New** or use `Ctrl+Alt+N` to create a document. Each open document has its own tab. Select a tab to switch documents.

### Rename, duplicate, and close

Use **Rename** or `F2` to rename the current document. Use **Duplicate** or `Ctrl+Alt+D` to create a copy. Use **Alt+W** to close the current document.

You can move a tab with `Alt+Shift+Left` or `Alt+Shift+Right`, and switch directly to a tab with `Ctrl+Alt+1` through `Ctrl+Alt+9`.

### Editing preferences

Open the **Editor** section in the sidebar to configure:

- Line numbers.
- Word wrapping.
- Browser spellcheck.
- Editor font.
- Font size.
- Line height.
- Tab width.

The toolbar's **A-** and **A+** controls also adjust editor text size.

## 3. Finding text

- **Find** or `Ctrl+F` opens find and replace for the active document.
- Enable **Match case** to make search case-sensitive.
- Enable **Whole word** to restrict matches to whole words.
- Use **F3** and **Shift+F3** to move between matches.
- **Replace** changes the selected match; **Replace all** applies the replacement throughout the active document.
- **Search all** or `Ctrl+Shift+F` searches across open documents and lets you jump to a result.

## 4. Appearance

Open the **Appearance** section in the sidebar to choose a design language and colour theme. Pass 3 includes 41 design languages and 40 built-in colour themes.

You can also create custom themes, browse and favourite looks, review recent combinations, and save appearance presets. Appearance choices are part of the browser-stored workspace settings and workspace backup.

## 5. Opening and saving files

The app offers distinct commands for distinct file actions:

### Open

Choose **Open…** or press `Ctrl+O`. The file is opened as a document in the editor. The app accepts common text formats: TXT, TEXT, MD, MARKDOWN, LOG, JSON, and CSV. A single opened text file must be no larger than 8 MiB.

### Save

Choose **Save** or press `Ctrl+S` to write changes to the file associated with the current document. The app shows a separate file status so it does not confuse saving to a computer file with autosaving the browser workspace.

If the browser reports that the file changed externally, review the status before saving. The app includes checks intended to avoid silently overwriting a file that changed on disk.

### Save As

Choose **Save As…** or press `Ctrl+Shift+S` to select a file destination for the current document.

### Export Copy

**Export Copy** downloads an independent text copy. It does not replace the linked file or mark that linked file as saved.

### Browser differences

Where supported, the app uses the File System Access API for file handles and write access. Other environments use file input and download fallbacks. Browser permission rules and available APIs determine the exact flow.

File associations are session-only. After a page reload, documents and settings can be restored from browser storage, but the app does not retain file-system handles. Reopen or reassociate a file to continue using the linked-file Save workflow.

## 6. Workspace backup and restore

Open the **Workspace** section in the sidebar.

- **Back up workspace** downloads a JSON backup containing documents, settings, custom themes, favourites, recent appearance history, recent documents, and saved presets.
- **Restore backup** validates a selected backup before applying it. Restore replaces the current workspace content, so export a fresh backup first if you need to preserve the current state.

The backup format has an application identifier and version. Pass 3 supports backup versions 1 and 2.

## 7. Keyboard shortcuts

See [Keyboard Shortcuts](KEYBOARD-SHORTCUTS.md) for the complete in-app shortcut reference.

## 8. Protecting your work

Browser storage is convenient, but it is not a permanent backup. Keep periodic workspace JSON backups and separate copies of important documents. Clearing site data, using private browsing, or switching browser profiles can make the stored workspace unavailable.

See [Storage and Privacy](STORAGE-AND-PRIVACY.md) for details.
