
# Dooksa eslint shared config

Dooksa's shared ESLint configuration. This package provides a strict, standardized linting setup utilizing ESLint's new Flat Config format, heavily focused on code style via `@stylistic/eslint-plugin` and JSDoc validation via `eslint-plugin-jsdoc`.

## Usage

This package exports an array of configuration objects designed for ESLint's Flat Config format (`eslint.config.js` or `eslint.config.mjs`).

Create an `eslint.config.js` file at the root of your project and import the config:

```javascript
import dooksaConfig from '@dooksa/eslint'

export default [
  // Spread the shared config directly into the array
  ...dooksaConfig,
  
  // Add any project-specific overrides here
  {
    rules: {
      // Example: override a specific rule for this project
      '@stylistic/js/indent': ['error', 4]
    }
  }
]

```

## What's included

* **Stylistic Formatting:** Enforces consistent spacing, indentation, quotes, and braces via `@stylistic/js`.
* **JSDoc Validation:** Ensures documentation consistency via `eslint-plugin-jsdoc`.
* **Default Ignores:** Automatically ignores common build and output directories (like `dist/`, `.history/`, and `playwright-report/`).

## License

[AGPL-3.0-only](https://www.gnu.org/licenses/agpl-3.0.en.html) © Thomas David