# Pantry Assistant v0.9a — offline-first PWA

This package is a PWA conversion of the tested v0.8 HTML app. **No Firebase SDK, user accounts, database, or cloud data upload is included.** The `firestore.rules` file is a deny-all starting point for the *later* cloud milestone; it is not used by GitHub Pages.

## Deploy from an Android phone
1. Sign in to github.com in Chrome and create a public repository called `pantry-assistant` (with a README or empty).
2. Upload the **contents** of this package (not the zip itself) at the repository root. Keep the `icons/` folder path. If your phone's GitHub mobile web UI doesn't support bulk folder upload, use `Add file → Create new file` for the three text files and create `icons/icon-192.png` and `icons/icon-512.png` through GitHub's Upload files UI, or upload via a computer later.
3. In the repository, open **Settings → Pages → Build and deployment** and choose **Deploy from a branch**, the `main` branch, and `/(root)`. Save.
4. Visit `https://YOUR_USERNAME.github.io/pantry-assistant/` in Chrome when Pages finishes publishing. On Android Chrome use the menu → **Install app** (wording may vary).
5. Open the installed app, add a disposable test item and close/reopen it. Then test airplane mode, navigation, recipes and shopping.
6. To move real data: in v0.8 open Data → Export backup. Save the JSON in Downloads. In the hosted v0.9a open Data → Import and select the file; verify counts, recipes and meal plans.

## Important safeguards
- Do not upload pantry backup JSON, account credentials, Firebase service account files, or private keys to a public GitHub repo.
- Keep v0.8 and a separate JSON backup until v0.9a migration has passed.
- Local storage is not synchronized across devices and can still be deleted by the browser.
- Since v0.9a caches its app shell, after updating code you must bump the `CACHE` name in `sw.js` to deliver an updated offline version reliably. A cache-first strategy is intentionally simple for this initial release.
- **Cloud rollout is gated:** Firebase Authentication, household permissions, two-account rules tests, transactional stock updates, and recovery tests must be completed before real data is uploaded.
