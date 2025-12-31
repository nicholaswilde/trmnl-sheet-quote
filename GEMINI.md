# Project Context: TRMNL Sheet Quote

## Overview
This is a **Private Plugin** for [TRMNL](https://usetrmnl.com), an e-ink display platform. The plugin fetches and displays quotes from a Google Sheet. It uses Liquid templates for rendering the UI on the e-ink screen and YAML for configuration.

The plugin operates by polling a Google Sheet's CSV export URL.

## Architecture & Technologies
*   **Platform:** TRMNL (Private Plugin)
*   **Templating:** [Liquid](https://shopify.github.io/liquid/) (`.liquid` files in `src/`)
*   **Configuration:** YAML (`src/settings.yml`)
*   **Data Source:** Google Sheets (via CSV export)
*   **Runtime:** The plugin runs within the TRMNL environment; there is no local Node.js or Python server to run. `package.json` exists primarily for metadata.

## Key Files
*   `src/settings.yml`: The core configuration. Defines the `polling_url` (Google Sheet CSV export), the user-facing input fields (Spreadsheet ID, column indices), and metadata.
*   `src/full.liquid`: The main view template for the full-screen layout.
*   `src/half_horizontal.liquid`, `src/half_vertical.liquid`, `src/quadrant.liquid`: Templates for other TRMNL layout sizes.
*   `src/img/`: Contains assets like the plugin icon and screenshot.

## Development & Usage

### "Building"
There is no compilation step. The source code *is* the distribution.
To "deploy" or "install":
1.  The `src/` directory is the plugin bundle.
2.  In a standard TRMNL development setup, this folder would be copied to the user's plugins directory.

### Running/Testing
*   **Local Testing:** Since this relies on the TRMNL environment to parse `settings.yml` and render `.liquid` with the fetched data, local testing typically requires a TRMNL simulator or uploading the plugin to a private TRMNL account.
*   **Data Flow:**
    1.  TRMNL reads `settings.yml`.
    2.  It constructs the polling URL using the user-provided `spreadsheet_id`.
    3.  It fetches the CSV data.
    4.  It passes the data to the `.liquid` templates to render the image.

### Conventions
*   **Structure:** Keep all plugin source files inside `src/`.
*   **Templating:** Use standard Liquid syntax. Ensure layouts handle dynamic content length gracefully (e.g., long quotes) given the small e-ink screen.
*   **Configuration:** Changes to plugin behavior (like adding new user inputs) happen in `src/settings.yml`.
*   **Versioning:** Update `package.json` version for semantic versioning tracking, even if not used for building.

## Common Tasks
*   **Update Layout:** Modify `src/*.liquid` files.
*   **Change Data Source Logic:** Edit the `polling_url` or `custom_fields` in `src/settings.yml`.
*   **Update Metadata:** Update `src/settings.yml` (description, author) and `package.json`.
