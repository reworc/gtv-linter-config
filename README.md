# Using the GTV ESLint configurations

1. Run `npm i @gesellschaftfuertechnischevisualistik/eslint-config --save-dev` to install the GTV ESLint configuration. Take note of the messages about missing peer dependencies.
2. Update or install any missing peer dependencies noted in the previous step, which may be any of: `npm i eslint @typescript-eslint/eslint-plugin @typescript-eslint/parser eslint-plugin-jsdoc --save-dev`. If you are unsure what peer dependencies are required, run `npm view @gesellschaftfuertechnischevisualistik/eslint-config peerDependencies`
3. Add a file named `.eslintrc.js` in the project root, setting up ESLint the use of the GTV ESLint configurations. Here's an example file for a project that uses TypeScript, ECMAScript 6 (2015) idioms and modules, as well as jQuery, and jsdoc for documentation:
    ```
    module.exports = {
    root: true,
    parser: '@typescript-eslint/parser',
    env: {
        'browser': true,
        'es6': true,
        'jquery': true
    },
    parserOptions: {
        'sourceType': 'module',
        'project': './tsconfig.json',
        'ecmaVersion': 6
    },
    extends: [
        '@gesellschaftfuertechnischevisualistik/eslint-config/eslint-config-ts',
        '@gesellschaftfuertechnischevisualistik/eslint-config/eslint-config-jsdoc'
    ]
    };
    ```
4. Run ESLint to see if everything works as intended: `./node_modules/.bin/eslint -c .eslintrc.js . --ext .ts` for typescript projects.
5. Configure your IDE to use ESLint to check automatically. In VS Code it should be enough to install the ESLint extension and everything should be picked up automatically.
