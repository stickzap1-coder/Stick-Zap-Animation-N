# StickZap Creator Studio — Safe Update Guide

## What was changed
- Event handlers are attached before the app waits for IndexedDB/local project storage. If browser storage is slow or unavailable, core controls should still respond.
- Startup now falls back to a new in-memory project if loading saved projects fails.
- No API keys or secrets are included in this ZIP.

## Before you update
1. Keep your current GitHub repository and Netlify site. Do not delete either.
2. If you have important saved projects in the app, export a project backup first if the app still allows it. Browser-local projects do not automatically transfer between browsers/devices.
3. Make sure the Netlify Git contributor restriction is resolved. Otherwise the new deploy may be blocked again.

## Android / GitHub update
1. Download and extract this ZIP on your phone.
2. Open the extracted `StickZap-Creator-Studio` folder. You should see `index.html`, `app.js`, `styles.css`, `netlify/`, `icons/`, `netlify.toml`, and `package.json`.
3. Open your existing GitHub repository in Chrome. Do not upload the ZIP as a single file.
4. Upload the extracted project files and folders into the repository root, keeping the same folder structure. When GitHub asks whether to replace files with matching names, confirm the replacements for the project files. Keep unrelated files if you need them.
5. Commit the changes to your existing production branch (usually `main`).
6. Open Netlify → your site → Deploys. Confirm a new deploy starts and ends as Published.
7. If it says unrecognized Git contributor, stop and fix that restriction first; repeatedly uploading the same files will not solve it.
8. Open `https://stickzap.netlify.app/` in Chrome and refresh. If an installed home-screen app still behaves differently, close it and reopen after the website deploy is Published.

## Important limits
- The nine included automated backend tests pass locally, and `app.js` passes Node's syntax check. These checks do not prove the live deployment or every button works on every phone.
- AI story/image/video features require the appropriate API access, Netlify Functions deployment, and valid environment variables. Video generation may have separate usage limits and costs.
- Keep `GEMINI_API_KEY` in Netlify environment variables only. Never paste it into GitHub files or screenshots.
