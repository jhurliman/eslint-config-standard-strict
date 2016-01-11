# eslint-config-standard-strict
ESLint config for ES7, following StandardJS with added checks

## Usage

1. Add all of the `"devDependencies"` listed in [package.json](https://github.com/jhurliman/eslint-config-standard-strict/blob/master/package.json) to your project's `"devDependencies"` section.

2. Add an additional entry to `"devDependencies"`:

    ```json
    "eslint-config-standard-strict": "latest"
    ```

3. Add a root level `.eslintrc` that references this package

    ```json
    { "extends": "standard-strict" }
    ```

4. Add another `.eslintrc` to your `test` folder that supports mocha

    ```json
    {
      "extends": "standard-strict",
      "env": { "mocha": true }
    }
    ```

5. (Recommended) Add the following entries to your `package.json` for simplified CLI access to linting:

    ```json
    "scripts": {
      "lint": "./node_modules/.bin/eslint .",
      "lint-changed": "git diff --name-only --cached --relative | grep '\\.js$' | xargs ./node_modules/.bin/eslint"
    }
    ```

6. (Recommended) Setup your editor to support inline ESLint support. For Sublime Text, that means `npm install -g eslint` then installing `SublimeLinter` and `SublimeLinter-contrib-eslint` packages. For Vim, use [Syntastic](https://github.com/scrooloose/syntastic).
