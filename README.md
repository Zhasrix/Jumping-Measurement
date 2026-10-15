# KineticJump Pro

A browser-based smartphone IMU vertical-jump analysis interface with athlete and coach views, a synthetic jump simulator, waveform visualization, local trial history, and SPSS-compatible CSV export.

## Run locally

1. Download or clone this repository.
2. Open `index.html` in a modern browser.
3. Choose **Desktop / Manual Simulation Mode** to try the simulator without phone sensors.

Some browser sensor APIs require HTTPS or localhost. For hardware sensor testing, serve the page over HTTPS and use a compatible mobile browser.

## Publish with GitHub Pages

1. Create a GitHub repository (for example, `kineticjump-pro`).
2. Upload the files in this folder to the repository root.
3. Open **Settings → Pages**.
4. Under **Build and deployment**, choose **Deploy from a branch**.
5. Select the `main` branch and `/(root)`, then save.
6. Wait for GitHub Pages to publish the site; the URL will appear in the Pages settings.

The entry point is `index.html`. `.nojekyll` is included for straightforward static-site publishing.

## Dependencies and network behavior

The page loads Tailwind CSS from `https://cdn.tailwindcss.com` and Chart.js 4.4.1 from jsDelivr, so those features require internet access unless the dependencies are bundled locally.

The application source includes a Google Apps Script cloud endpoint for coach polling/synchronization. Review and configure that endpoint before public deployment. Do not publish private credentials or sensitive athlete data. Browser trial history is stored in `localStorage` on the user's device.

## Important notes

- This repository is a static HTML app; no Node.js build step is required.
- The interface describes biomechanical analysis features, but measurements from phone sensors can be noisy and should not be treated as clinical-grade or validated measurements without independent testing.
- The current source does not include a separate web app manifest or service-worker file. The in-page offline-install message should not be interpreted as proof that full offline caching is configured.
- Test sensor permissions, CSV export, simulation, and cloud connectivity after deployment.

## Project structure

```text
.
├── index.html
├── README.md
├── .nojekyll
├── .gitignore
└── LICENSE
```
