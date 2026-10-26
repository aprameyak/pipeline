# Pipeline

A small job application tracker. Log each application with its company, role, and stage, and see how many sit at each step from applied to offer.

## Features

- Log applications with company, role, stage, applied date, and an optional expected salary
- Four stages: applied, screening, interview, offer
- Stage counts shown as a row of totals above the list
- Entries are saved to a local JSON file, so they survive a server restart

## Getting started

Requires Node.js.

```bash
npm install
npm start
```

Then open http://localhost:3012. `npm run dev` runs the same command.

## How it works

- `index.html` is the whole frontend: a form for new applications and a list with stage counts. It calls the API at `http://localhost:3012`.
- `server.js` is an Express app that serves the page and exposes two endpoints:
  - `POST /api/applications` saves an application.
  - `GET /api/applications` returns all applications plus per-stage counts. Pass `?stage=interview` (or any stage) to filter the list.
- Data is written to `data.json` in the project folder, which is created on first run and ignored by git.
- `utils.js` holds validation and file helpers that are not yet wired into `server.js`.

## Status

Prototype. Single user, no accounts, and no way to edit or delete an application from the UI.

## License

MIT, see [LICENSE](LICENSE).
