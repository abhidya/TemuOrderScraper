# TemuOrderScraper

Browser-only Temu invoice helper. It accepts a Temu purchases spreadsheet or CSV, extracts order IDs, and builds Temu order-detail links/iframes for printing or opening in tabs.

## Demo

- Primary page: `Main.html`
- Alternate experiments: `Main_optionB.html.html` and `Main_sequential.html.html`

This can be hosted as a static GitHub Pages demo because there is no backend. The page fetches the SheetJS parser from jsDelivr and opens Temu order-detail URLs in the user's browser.

## Run locally

Serve the folder with any static file server:

```sh
python3 -m http.server 4173
```

Then open:

```text
http://localhost:4173/Main.html
```

## Expected input

- `.xlsx`, `.xls`, or `.csv`
- A column named like `Order ID`, `order_id`, `URL`, or `link`
- Full Temu URLs are accepted if they include `parent_order_sn`

## Notes

- Temu may block iframes or require a logged-in browser session. Use **Open all in tabs** when iframe loading is blocked.
- The CSV parser is intentionally lightweight and assumes simple comma-separated rows without quoted commas.
- No purchase data is uploaded by this tool; parsing happens in the browser.
