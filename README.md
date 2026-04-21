# mdtool — Support

**mdtool** is a fast, native macOS markdown viewer and editor. Write on the left, see the rendered result on the right, and browse your entire notes folder from a built-in sidebar. Works entirely offline — no account, no sync, no telemetry.

Get it on the [Mac App Store](https://apps.apple.com/app/mdtool/).

---

## Contact

For bug reports, feature requests, or general questions, please open an issue in this repository:

**https://github.com/nautikasupport/mdtool/issues**

We read every issue and respond as quickly as we can.

If you prefer email, you can also reach us at **support@nautika.corp**

---

## Features

- **Live side-by-side preview** — edit on the left, rendered output updates on the right as you type.
- **Folder browser** — open a folder once and navigate your markdown files in a tree-style sidebar.
- **Recent files** — persistent recent files list survives relaunches.
- **GitHub Flavored Markdown** — tables, task lists, strikethrough, autolinks, fenced code blocks.
- **PDF export** — press `⌘⇧E` to export the current document as a print-ready PDF.
- **Dark mode** — automatic light/dark theme matching system appearance.
- **Zoom controls** — `⌘=`, `⌘-`, `⌘0` to adjust preview zoom.
- **Autosave** — edits are saved automatically after a short pause.

## Supported file types

`.md`, `.markdown`, `.mdown`, `.mkd`

## Keyboard shortcuts

| Shortcut | Action |
|---|---|
| `⌘O` | Open file |
| `⌘⇧O` | Open folder |
| `⌘S` | Save |
| `⌘⇧E` | Export to PDF |
| `⌘=` | Zoom in |
| `⌘-` | Zoom out |
| `⌘0` | Reset zoom |

## System requirements

- macOS 13.0 or later
- Apple silicon or Intel

---

## Frequently asked questions

### Where does mdtool store my files?
mdtool never moves or copies your files. Everything you edit is saved in place, in the exact folder and filename you opened. mdtool only remembers which folder and which recent files you've opened (via secure bookmarks stored in the app's sandbox container).

### Does mdtool sync to iCloud or any other service?
No. mdtool does not sync anywhere. If you want iCloud sync, put your markdown files in an iCloud Drive folder and open that folder in mdtool — macOS handles the sync transparently.

### Can mdtool open files that aren't markdown?
mdtool opens any plain-text file with a markdown extension: `.md`, `.markdown`, `.mdown`, `.mkd`. Non-markdown text files aren't supported in this version.

### Why does editing a large file cause a brief flicker?
The preview reloads whenever the document changes, and very large files (hundreds of KB) can take a moment to re-render. This is expected. Future versions may add incremental updates.

### Can I open files or folders from Terminal?
Yes. Save the following as `/usr/local/bin/mdtool` (or anywhere on your `PATH`) and make it executable:

```sh
#!/bin/sh
# Open a folder (or file) in the mdtool Mac app.
#   mdtool            -> opens the current working directory
#   mdtool path/...   -> opens that folder or file
if [ $# -eq 0 ]; then
    target="$PWD"
else
    target="$1"
fi
exec /usr/bin/open -a mdtool "$target"
```

Then run `chmod +x /usr/local/bin/mdtool`. After that, `mdtool`, `mdtool notes/`, and `mdtool README.md` all launch the app on the given path.

### How do I report a bug?
Open an issue at https://github.com/nautikasupport/mdtool/issues with:
- Your macOS version
- Your mdtool version (in the About window)
- Steps to reproduce the problem
- What you expected to happen vs. what actually happened

Screenshots help a lot.

### Is mdtool open source?
The application itself is not open source. It uses the MIT-licensed [cmark-gfm](https://github.com/github/cmark-gfm) library for markdown parsing; acknowledgments are available in mdtool's **About** window.

---

## Privacy Policy

**mdtool does not collect, store, transmit, or share any user data.**

- mdtool does not use analytics, telemetry, advertising, tracking, crash reporting, or any third-party services.
- mdtool does not make network requests. It runs entirely on your Mac.
- mdtool does not require an account, email address, or any other personal information.
- Your files, their contents, and the list of files you've opened never leave your device.

The only data mdtool stores is a local list of bookmarks to folders and files you've opened, kept inside the app's sandbox container on your Mac. This list is used solely to restore your last folder and recent files on the next launch. It is never transmitted anywhere.

mdtool requests the following macOS sandbox permissions:

- **User-selected file read/write** — so you can open and save your markdown files.
- **Outgoing connections** — required by macOS for WebKit to render the preview; no actual network requests are made by the app.

If you have any questions about privacy, open an issue in this repository or contact **support@nautika.app**.

Last updated: 2026-04-07

---

Copyright © 2026 Nautika. All rights reserved.
