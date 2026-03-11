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

### JSDoc Rules

* **`jsdoc/require-jsdoc`:** Requires JSDoc comments on all public declarations (functions, methods, classes, arrow functions). Ensures every entry point is documented.
* **`jsdoc/check-tag-names`:** Validates custom tag usage (`note`, `overload`, `query-parameters`, `returns-error`, `returns-response`, `returns-success`, `supported-operators`, `supported-values`). Warns on undefined tags to maintain documentation consistency.
* **`jsdoc/require-param-description`:** Enforces descriptions for all parameters in JSDoc comments.
* **`jsdoc/require-param-type`:** Requires explicit type annotations for all parameters.
* **`jsdoc/check-syntax`:** Validates JSDoc syntax correctness to prevent malformed documentation.
* **Custom Type Definitions:** Recognizes common types including `Buffer`, DOM elements (`Element`, `HTMLElement`, etc.), Node.js globals, and internal utility functions (`validateSchemaArray`, `validateSchemaObject`, etc.).

### Stylistic Formatting Rules (`@stylistic/js`)

* **`curly-newline`:** Always places curly braces on a new line.
* **`indent`:** Enforces 2-space indentation with specific offsets for SwitchCase, VariableDeclarator, outerIIFEBody, MemberExpression, and Function parameters. CallExpression arguments are indented at the same level as the function call.
* **`object-curly-spacing`:** Requires spaces inside curly braces `{ }`.
* **`object-property-newline`:** Enforces newline rules for object properties.
* **`object-curly-newline`:** Requires multiline formatting with consistent spacing for objects, patterns, imports, and exports.
* **`quote-props`:** Uses unquoted property names only when necessary (as-needed).
* **`space-before-function-paren`:** Always includes a space before function parentheses `function( )`.
* **`function-call-spacing`:** Never allows spaces inside function call parentheses `( )`.
* **`implicit-arrow-linebreak`:** Requires arrow functions to be on the same line as their expression.
* **`eol-last`:** Enforces Unix-style line endings with a trailing newline.
* **`brace-style`:** Follows the 1tbs (Google) style, disallowing single-line blocks.
* **`semi`:** Disallows semicolons entirely (ASI usage).
* **`quotes`:** Requires single quotes for strings, allowing template literals when appropriate.
* **`comma-dangle`:** Never allows trailing commas in arrays or objects.
* **`comma-spacing`:** No space before comma, space after comma.
* **`comma-style`:** Places commas at the end of the line (last style).
* **`array-bracket-spacing`:** No spaces inside array brackets `[ ]`.
* **`array-bracket-newline`:** Consistent newline rules for array elements.
* **`array-element-newline`:** Consistent newline rules between array elements.
* **`computed-property-spacing`:** No spaces inside computed property brackets `[ ]`.
* **`no-mixed-operators`:** Prohibits mixing different operator types in the same expression (e.g., arithmetic with bitwise, comparison with logical). Groups: math operators, bitwise operators, comparison operators, logical operators, and `in`/`instanceof`.
* **`key-spacing`:** Strict spacing between object keys and values.
* **`no-trailing-spaces`:** Disallows trailing whitespace on lines.
* **`no-multi-spaces`:** Disallows multiple spaces in a row (except where explicitly allowed).
* **`no-confusing-arrow`:** Prevents arrow functions that could be confused with block statements.

## License

[AGPL-3.0-only](https://www.gnu.org/licenses/agpl-3.0.en.html) © [Thomas David](https://thomasjackdavid.com)
