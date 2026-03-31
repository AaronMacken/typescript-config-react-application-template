# @aaronmacken/typescript-config-react-application-template

Shared TypeScript config for React application templates.

This package publishes a single `tsconfig.json` you can extend in app projects.

## Installation

Install from GitHub Packages:

```bash
npm install -D @aaronmacken/typescript-config-react-application-template@1.0.0
```

## Usage

In your app's `tsconfig.json`:

```json
{
  "extends": "@aaronmacken/typescript-config-react-application-template/tsconfig.json"
}
```

## What This Config Includes

- `module` and `target`: `ESNext`
- `jsx`: `react-jsx`
- `moduleResolution`: `node`
- `noImplicitAny`: `true`
- `skipLibCheck`: `true`
- `allowJs`: `true`
- `allowSyntheticDefaultImports`: `true`
- `esModuleInterop`: `true`
- `include`: `src/**/*`
- `baseUrl`: `./src`
- Path aliases:
  - `@components`, `@components/*`
  - `@context`, `@context/*`
  - `@hooks`, `@hooks/*`
  - `@utils`, `@utils/*`
  - `@constants`, `@constants/*`
  - `@customTypes`, `@customTypes/*`

## Important Notes

- The aliases above assume your app source folder is `src`.
- If your folder structure differs, override `compilerOptions.baseUrl` and `compilerOptions.paths` in your app-level `tsconfig.json`.

## npm Registry Setup (Consumer App)

Add to repo-level `.npmrc`:

```ini
@aaronmacken:registry=https://npm.pkg.github.com
//npm.pkg.github.com/:_authToken=${GITHUB_PACKAGES_AUTH_TOKEN}
always-auth=true
```

Set environment variable on each machine:

- `GITHUB_PACKAGES_AUTH_TOKEN=<your_github_pat>`

Minimum token scope for install:

- `read:packages`

Additional scopes for publishing:

- `write:packages`
- `repo` (if repository/package is private)

## Releasing a New Version

1. Update `tsconfig.json` as needed.
2. Bump `version` in `package.json`.
3. Commit: `git add . && git commit -m "chore: describe change"`
4. Tag: `git tag -a v1.0.1 -m "release v1.0.1"`
5. Push: `git push origin master --follow-tags`
6. Publish: `npm publish`

## Consuming an Update in an App

```bash
npm install -D @aaronmacken/typescript-config-react-application-template@1.0.1
```
