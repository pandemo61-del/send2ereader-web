# send2ereader-web

A simple web app that recreates the same functionality as the original `send2ereader` project: a desktop browser uploads an ebook or URL, and a Kobo/Kindle browser device receives the temporary download link using a shared 4-character key.

## Features

- Generate a unique key for the receiving device
- Upload EPUB, MOBI, PDF, TXT, CBZ, CBR, and URL links
- Keep uploaded files temporarily available for the receiver
- Detect the receiving device type and apply device-specific conversion
- Convert CBZ/CBR comics to a PDF with one detected panel per page, using black, white, or solid-color gutters
- Remove small page numbers from the bottom margins of converted comic pages
- Choose a Kobo or Kindle screen profile, or enter a custom resolution for comic PDFs
- Poll for file readiness on the receiver page

## Run locally

```bash
npm install
npm start
```

Then open:

- http://localhost:3002 for the web app

## Notes

The server expects external conversion tools when needed:

- `kepubify`
- `kindlegen`
- `pdfcropmargins`

If those binaries are not installed, upload will still work for non-converted files, and the server will return a clear error for conversion attempts.
