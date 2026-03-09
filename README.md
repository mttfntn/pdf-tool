# MTTFNTN — PDF Tool

A fully client-side PDF toolkit for compressing, editing, signing, and converting. No server, no uploads, no dependencies — everything runs in the browser.

## Features

### PDF Compression

- Re-renders every page as JPEG at adjustable quality (10–100%)
- Rebuilds the PDF using object streams for smaller file size
- Option to strip all metadata (title, author, subject, keywords, producer, creator)
- Batch compression across multiple files with per-file progress

### Page Management

- **Visual page view** — open any PDF to see full-page canvas renders
- **Page selection** — Click to select, Ctrl/Cmd+Click to toggle, Shift+Click for ranges
- **Delete pages** — remove selected pages from a PDF
- **Reorder pages** — drag and drop pages to rearrange order
- **Select All** for quick bulk operations

### Signature Overlay

- Load a signature image (PNG, JPEG, or WebP)
- Visual page picker with thumbnails to choose which page to sign
- **Interactive positioning** — drag the signature overlay directly on the page
- **Resize handle** — drag the corner handle to scale the signature
- **Fine-tune sliders** — X position, Y position, and size (all synced with drag)
- Applies the signature permanently into the PDF

### Image to PDF

- Drop images (JPEG, PNG, WebP, GIF, BMP, TIFF/TIF) to create a new PDF
- TIFF support via built-in decoder
- Configurable page size: A4, Letter, Legal, or Fit to image
- Adjustable margin (0–200 px)
- One image per page option

### Batch Processing

- Drag & drop or click to browse — supports multiple PDFs and images at once
- **Multi-select**: Click to select, Ctrl/Cmd+Click to toggle individual files, Shift+Click to select ranges
- **Remove selected** or **Clear all**
- File list showing name, size, page count, and status
- Bottom bar with file count, total pages, and total size

### Export Options

- Customizable output filename or same-as-input naming
- Download individual PDFs from page view
- Batch compress & download all loaded files

### UI

- Dark theme with orange accent (`#FF4D00`)
- Real-time status pill: green (ready), purple (loading), red (error)
- Bottom bar with file count, total pages, and combined size
- Toast notifications for quick feedback

## How It Works

Everything runs in the browser. The HTML file loads a few local library files — no build step, no package manager, no external requests.

**Bundled libraries (inline):**

| Library | Purpose |
|---------|---------|
| pdf-lib | PDF creation, editing, page manipulation, and image embedding |
| pdf.js | PDF rendering to canvas (page previews and compression pipeline) |
| UTIF.js | TIFF/TIF image decoding |

**Custom implementations (no external library):**

- Drag-and-drop page reordering with visual feedback
- Interactive signature overlay with drag, resize, and slider sync
- JPEG-based compression pipeline (pdf.js render → canvas → JPEG → pdf-lib rebuild)
- TIFF to PNG conversion pipeline for image-to-PDF workflow

## Installation

There's nothing to install. No `npm install`, no build tools, no frameworks, no Docker, no server. It's a single HTML file with all dependencies bundled inline. Just open `pdf-tool.html` in your browser.

No internet connection needed — everything is self-contained.

## Usage

1. Open `pdf-tool.html` in any modern browser
2. Drop PDFs or images onto the drop zone (or click to browse)
3. Double-click a PDF to open the page view for editing, reordering, or signing
4. Adjust compression, signature, or export settings in the right panel
5. Click **Compress & Download All** or **Download PDF**

## Browser Compatibility

Works in all modern browsers (Chrome, Firefox, Edge, Safari).

## Credits

This project uses the following open-source libraries:

- **[pdf-lib](https://github.com/Hopding/pdf-lib)** — Create and modify PDF documents in any JavaScript environment (MIT)
- **[PDF.js](https://github.com/nicolo-ribaudo/pdfjs-dist)** — Mozilla's PDF rendering library (Apache 2.0)
- **[UTIF.js](https://github.com/nicolo-ribaudo/UTIF.js)** — TIFF decoder in JavaScript (MIT)

## Author

Created with love by Matteo Fontana.

## License

MIT License

2026 Matteo Fontana

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.