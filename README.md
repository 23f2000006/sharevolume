# SEC Entity Shares Outstanding Viewer

This single-page application (SPA) allows you to view the maximum and minimum shares outstanding for a given SEC CIK (Central Index Key) from publicly available SEC data.

## Features

- **Dynamic Data Fetching**: Fetches `EntityCommonStockSharesOutstanding` data directly from the SEC API.
- **Filtering**: Displays data for fiscal years (FY) greater than 2020.
- **Max/Min Calculation**: Identifies and highlights the highest and lowest shares outstanding within the filtered period.
- **Responsive Design**: Built with Tailwind CSS for a modern, mobile-friendly interface.
- **Dynamic CIK Input**: Supports viewing data for any 10-digit CIK by appending `?CIK=YOUR_CIK_NUMBER` to the URL.

## Usage

To view data for a specific company, open `index.html` in your web browser. By default, it displays data for Aflac (CIK: 0000004977).

To view data for a different company, append a `CIK` query parameter to the URL. For example:

```
index.html?CIK=0001018724
```

Replace `0001018724` with the desired 10-digit CIK.

### Technical Details

- The application uses `fetch()` to retrieve data from `https://data.sec.gov/api/xbrl/companyconcept/`. Due to Cross-Origin Resource Sharing (CORS) policies enforced by `data.sec.gov`, a public CORS proxy (`https://api.allorigins.win/raw?url=...`) is used for client-side requests. For production environments, it is recommended to implement a custom backend proxy to manage SEC API requests more robustly and handle potential rate limits.
- A descriptive `User-Agent` header (`MyApp/1.0 (myemail@example.com)`) is included in API requests as per SEC guidance.

## Local Development

1. Save the provided `index.html` file to your local machine.
2. Open `index.html` in your web browser.

No build steps are required as all dependencies are loaded via CDN and inline scripts.

## Attachments

This project includes the following attachment:

### `uid.txt`

```
Unique Identifier: 0c7b9a2e-4f1d-4c8a-9e0a-3d2b1c0e9f8a
```
