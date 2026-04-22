# Getting Started with Create React App

This project is an Airbnb-like front-end built with React and Material UI. It was bootstrapped with Create React App (CRA).

## Quick links

- Start (dev): `npm start`
- Install deps: `npm install`
- Build (prod): `npm run build`

## Prerequisites

- Node.js (16.x or later recommended)
- npm (comes with Node) or an alternative package manager (Yarn, pnpm). The instructions below use npm and Windows PowerShell.

## Install

Open a PowerShell terminal in the project root (`i:\airbnb-clone`) and run:

```powershell
npm install
```

This will install dependencies listed in `package.json`.

## Run (development)

Start the development server (CRA):

```powershell
npm start
```

By default the app runs at http://localhost:3000. If that port is busy, CRA will offer another port and show it in the terminal.

## Build (production)

Create an optimized production build:

```powershell
npm run build
```

The `build/` folder will contain the production assets.

## Project structure (important files)

- `src/` — application source
	- `App.js` — app entry
	- `components/` — UI components (Cards, Filter, Header, MobileSearchBar)
	- `assets/` — images and static data used by the UI
- `public/` — static public files (index.html, manifest)
- `package.json` — scripts & dependencies

## Known runtime / dev issues (observed)

When running this project locally the dev server starts successfully but the terminal may show a few warnings (non-blocking):

- ESLint warnings: some files use `==` instead of `===`, some `img` tags are missing `alt` attributes, and there are a few unused imports. These don't prevent the app from running but are good to fix for quality and accessibility.
- A create-react-app related message: `babel-preset-react-app` imports `@babel/plugin-proposal-private-property-in-object` without declaring it. To silence the message you can add it as a devDependency (see below).
- `npm install` may report audit warnings (vulnerabilities) typical for older CRA dependencies. Review and fix as needed.

Suggested quick fixes:

- Replace `==` with `===` where appropriate to match ESLint rules.
- Add `alt` attributes to decorative and meaningful `img` elements.
- Remove unused imports (e.g., `Box`, `Button`, or `useState` where they are not used).
- To silence the babel message, add the dev dependency and reinstall:

```powershell
npm install --save-dev @babel/plugin-proposal-private-property-in-object
```

- Run `npm audit` and `npm audit fix` to auto-fix some security issues. Use `--force` only after reviewing breaking changes.

## Linting and tests

This project uses the default CRA linting / testing setup. To run tests:

```powershell
npm test
```

ESLint runs automatically in the dev server; fix warnings by editing the files mentioned in the terminal output.

## Developer notes & tips

- When adding components follow the existing structure under `src/components/` and keep styles local (each component folder has `styles.css`).
- Assets (images and fonts) live under `src/assets/`.
- If you plan to upgrade major dependencies (React, MUI, react-scripts), do so carefully and run the app and tests after each upgrade.

## Contributing

1. Create a branch: `git checkout -b feat/your-feature`
2. Make changes and add tests where appropriate.
3. Run `npm install` and `npm start` to test locally.
4. Open a pull request.

## Troubleshooting

- If `npm start` fails with a port conflict, either stop the other server or run the app on a different port (CRA will prompt to use another port).
- If you see module resolution errors after changing dependencies, remove `node_modules/` and reinstall:

```powershell
Remove-Item -Recurse node_modules
npm install
```

## License

This repository does not include a license file. If you want to open-source it, consider adding a `LICENSE` (for example MIT).

---

If you'd like, I can also:

- Fix the ESLint warnings automatically (small code edits) and re-run the dev server.
- Add the suggested devDependency to eliminate the babel message and re-install.
- Run `npm audit fix` and show which vulnerabilities remain.

Tell me which follow-up you'd like and I'll do it.
