# Developer Knowledge Search

This small static site loads `data.json` via `fetch()` and renders results.

## Why the page may be blank when opened directly
If you open `index.html` from your filesystem (it shows as `file:///...` in the browser), the `fetch('data.json')` call will usually fail due to browser security (CORS/file protocol) and `data` will not be loaded. Browsers block these requests unless served via HTTP.

## How to run locally (quick options)

Option 1 — Python (works if you have Python 3 installed):

```powershell
# from the project folder:
python -m http.server 8000
# open browser at:
http://localhost:8000
```

Option 2 — Node (if you prefer a simple HTTP server):

```powershell
# using npx (no install needed):
npx http-server -p 8000
# open browser at:
http://localhost:8000
```

Option 3 — VS Code Live Server extension:
- Install Live Server
- Right-click `index.html` → "Open with Live Server"

## Other options
- Embed the `data.json` directly in `index.html` (scripting) if you do not wish to run a server.
- Add a small backend to host the JSON if needed.

## Keyword highlighting
When you search, matching keywords will now be highlighted inside result text. The search is case-insensitive and will highlight multiple words (space-separated). Toggle type buttons to filter and see highlight updates immediately.

### Tokenized search
You can search by multiple words (space-separated). All tokens must appear in the content for a match (AND semantics). Partial matches are allowed, which means `dev` will match `developer` and `i dev` will match `I am full stack developer`.

## Notes
- The page now shows a helpful error message if the fetch fails and tells you how to start a simple local server.
