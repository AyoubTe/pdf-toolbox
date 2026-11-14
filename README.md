# Local PDF Toolbox

A free, private PDF toolbox in **one HTML file**. Merge, split, extract, rotate, compress, convert and stamp your PDFs without uploading anything anywhere.

Everything runs inside your web browser, on your own computer. Your documents never leave it.

## Why this exists

Most online PDF tools make you upload your files to someone else's server. That is a bad idea for personal documents such as IDs, contracts, tax papers and medical records. This tool does the same jobs locally, so there is nothing to trust and nothing to leak.

## How to use it

1. Download `pdf-toolbox.html`.
2. Double-click it. It opens in your browser (Chrome, Edge, Firefox or Safari).
3. Drag your files in and pick a tool.

No installation, no account, no internet connection needed. You can turn off Wi-Fi and it still works.

## Features

| Tool | What it does |
|---|---|
| **Merge** | Combine several PDFs into one. Reorder by dragging, choose which pages to take from each file (`1-3, 5, 8-`). |
| **Extract / Split / Organize** | See page thumbnails. Select, rotate, delete, drag to reorder or reverse pages. Extract selected pages as a new PDF, or split into one file per page or every N pages (downloaded as a `.zip`). |
| **Compress** | Reduce file size. Four levels from lossless to maximum, with before/after sizes shown. Optionally removes metadata (title, author, dates). |
| **Images → PDF** | Turn JPG, PNG, WebP, GIF or BMP images into a PDF. Choose page size (A4, Letter, same as image), margin and quality. Photo rotation is respected. |
| **PDF → Images** | Save pages as PNG or JPEG at 72 to 300 dpi. One page gives an image, several give a `.zip`. |
| **Page numbers & Watermark** | Add page numbers and/or a text watermark to all or some pages. Works on rotated pages. |

### Compression levels

| Level | What happens | Text stays selectable? |
|---|---|---|
| Light | Lossless. Only compresses data that was not compressed yet. Often saves little. | Yes |
| Balanced | Shrinks the photos and scans inside the PDF (max ~1800 px). Recommended. | Yes |
| Strong | Smaller photos (max ~1100 px), lower quality. | Yes |
| Maximum | Turns every page into a compressed picture (~110 dpi). Smallest result. | **No** |

Compression works best on PDFs full of photos or scans. A PDF that is mostly text is already small, so there is little to gain. The tool shows you the result before you download, so you can keep your original if it did not help.

## Privacy and security

- **No uploads.** Files are read into your browser's memory and processed there. Nothing is sent anywhere.
- **Network blocked by the page itself.** The file contains a Content Security Policy that stops the browser from making any request to the internet, so even a bug could not send your data out.
- **Your originals are never modified.** The tool can only read the files you choose. Results are always saved as new files in your Downloads folder.
- **Nothing is stored.** No cookies, no local storage, no temporary files. Closing the tab clears everything.
- **You can check it.** It is a single readable HTML file with no hidden parts. You can run it offline, or watch the Network tab in your browser's developer tools while you use it.

Tip: browser extensions can sometimes read the pages you open. For maximum privacy, use a private window or a browser profile without extensions.

## Limitations

- **Password-protected PDFs** are not supported. Remove the password first.
- **Adding a password** (encrypting a PDF) is not supported.
- **Page numbers and watermarks** accept Latin letters, digits and common punctuation only (no Cyrillic, Chinese, Arabic and so on).
- **Merging and extracting** keep how pages look, but document bookmarks and some links or form fields in the originals may not be carried over.
- **Very large files** (hundreds of MB) can be slow, because everything is processed in memory.
- **Page thumbnails** use standard fallback fonts, so a few may look slightly different from the real page. The exported PDFs are not affected.
- **Maximum compression** removes the text layer (no search, copy or select).

## How it works

Plain HTML, CSS and JavaScript, with two open-source libraries embedded in the file so it needs no downloads:

- [pdf-lib](https://github.com/Hopding/pdf-lib) (MIT license) reads, builds and edits PDF files: merging, extracting, rotating, stamping.
- [PDF.js](https://github.com/mozilla/pdf.js) (Apache-2.0 license) draws PDF pages for thumbnails, PDF to image, and maximum compression.

Standard browser features do the rest: the File API reads your files, the Canvas API recompresses images, and Blob downloads save the results.

## Browser support

Current versions of Chrome and Edge are the best tested. Firefox and Safari should work, but the tool was developed and tested with Chrome.

## License and credits

Feel free to use that tool.

This tool includes third-party software, which keeps its own license:

- pdf-lib 1.17.1, MIT License, © Andrew Dillon
- PDF.js 3.11.174, Apache License 2.0, © Mozilla and contributors
