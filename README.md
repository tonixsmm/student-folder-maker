# Student Folder Maker

Browser-based utility for generating a ready-to-use folder tree for every student in a CSV. The app copies any template documents you provide, renames them per student, and bundles everything into a ZIP file.

## Features
- Works entirely client-side; your data never leaves the browser.
- Supports CSVs with or without headers (`LastName,FirstName`).
- Optional country presets pre-fill folder names and prefix rules (Italy and Spain included by default).
- Flexible rename rules that prepend numeric prefixes when filenames contain specific keywords.
- Sample template bundles for each country (`Italy_LA`, `Italy_SF`, `Spain`) to help you get started.

## Quick Start
1. Open `index.html` in a modern desktop browser (Chrome, Edge, Firefox, Safari).
2. Select a country preset or keep `Custom` values in the form fields.
3. Fill in/confirm the main folder name and ZIP filename.
4. Attach a CSV listing your students (see format below).
5. Attach one or more template files (DOCX, PDF, etc.).
6. (Optional) Add prefix rules to control numeric prefixes in the generated filenames.
7. Click **Generate ZIP** and save the download when prompted.

## CSV Format
- Expected columns: `LastName,FirstName`. Headers are optional.
- Extra columns are ignored.
- Example:

```csv
LastName,FirstName
Doe,Jane
Smith,John
Nguyen,Tony
```

If your CSV lacks headers, the app assumes the first column is the last name and the second is the first name.

## Prefix Rules
Define rules that add numeric prefixes when a template filename contains a specific substring. Use `KEY=NUMBER` pairs separated by semicolons.

Example: `SF_IT_STUDY=1;Mailing_Declaration=4`

In this case, any template filename containing `SF_IT_STUDY` will be prefixed with `1.`, while files containing `Mailing_Declaration` get `4.` when copied for each student.

This is helpful for ordering documents later in the visa process.

## Template Files
- Drop in any mix of DOCX, PDF, or other files. The originals are left untouched.
- Sample template folders in the repo (`Italy_LA`, `Italy_SF`, `Spain`) contain example documents you can use or replace with your own.

# Development Area
## Tech Stack
- [Papa Parse](https://www.papaparse.com/) for CSV parsing.
- [JSZip](https://stuk.github.io/jszip/) to build the ZIP archive client-side.
- [FileSaver.js](https://github.com/eligrey/FileSaver.js/) to trigger downloads.
- No build tools or server—just open the HTML file.

## Development
- Static project: open `index.html` directly or host it via any static file server.
- To make code changes, edit `index.html`; no bundling step is required.

## License
MIT License. See `LICENSE` file for details.
