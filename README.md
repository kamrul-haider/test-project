# test-project

A Node.js starter project. The package is set up with npm and uses [dotenv](https://github.com/motdotla/dotenv) to load environment variables from a `.env` file.

Application code is not in place yet. The intended stack (see `cursor.md`) is **TypeScript**, **Next.js** (App Router), and **React**.

## Requirements

- Node.js 12 or later (current LTS recommended)
- npm

## Setup

```bash
npm install
```

Create a `.env` file in the project root for local secrets. Do not commit it.

```env
# Example
# API_KEY=your-key-here
```

## Scripts

| Script | Description |
| --- | --- |
| `npm test` | Placeholder; no tests are defined yet |

Once the Next.js app is scaffolded, typical scripts will be `dev`, `build`, `start`, `lint`, and `typecheck`.

## Project layout

```text
package.json         # Package name, scripts, and dependencies
package-lock.json    # Locked npm dependency versions
cursor.md            # Stack and coding conventions for this repo
```

Planned layout when the app is added:

```text
app/                 # Next.js App Router: pages, layouts, API routes
components/          # Reusable React components
lib/                 # Shared utilities, clients, helpers
public/              # Static assets
types/               # Shared TypeScript types
```

## License

ISC
