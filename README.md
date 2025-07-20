# TRMNL Sheet Quote

A private plugin for [TRMNL](https://usetrmnl.com) to display quotes from a Google Sheet.

![sheet-quote](https://raw.githubusercontent.com/nicholaswilde/trmnl-sheet-quote/refs/heads/main/src/img/screenshot.png)

## :rocket: Features

-   Displays a random quote from a Google Sheet.
-   Customizable polling interval to fetch new quotes.
-   Configurable columns for quote and author.

## :hammer_and_wrench: Installation

1.  Clone this repository to your local machine.
2.  Copy the `src` directory to your TRMNL plugins directory.
3.  Rename the `src` directory to `sheet-quote`.

## :gear: Configuration

Configuration is handled within the TRMNL application. After installing the plugin, you will find the following settings:

-   **Spreadsheet ID**: The ID of your Google Sheet.
-   **Quote Column Index**: The column number (starting from 0) for the quotes in your sheet.
-   **Author Column Index**: The column number (starting from 0) for the authors in your sheet.

For more detailed instructions, please see the [TRMNL documentation](https://help.usetrmnl.com/en/articles/11400219-using-google-sheets-with-private-plugins).

## :construction: Development

This project does not have any dependencies to install or a development server to run. The plugin is designed to be used within the TRMNL application.

To make changes, edit the files in the `src` directory. The `.liquid` files control the layout, and `settings.yml` controls the configuration options.

## :balance_scale: License

This project is licensed under the Apache License 2.0. See the [LICENSE](LICENSE) file for details.

## :pencil:​ Author

​This project was started in 2025 by [Nicholas Wilde][2].

[2]: <https://github.com/nicholaswilde/>
