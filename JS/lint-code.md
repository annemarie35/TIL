# HOW TO LINT CODEBASE

## Format with prettier

- remove eslint config from package.json if existing
First, remove all existing elsint configuration because for example eslint can be added when installing React via some dependencies
Plus, it is better to keep configuration away from package.json and put it in a specific configuration file.

- install prettier in dev dependencies
In a react project, it is possible to install all dependencies as dev dependencies cause it will be build for production so it doesn't make much sense to separate dependencies by env.


```shell
npm i -D prettier
```

- add .prettierignore
Cause you don't need to lint all files in the project

```txt
node_modules
# Ignore artifacts:
build
coverage
```

- add config file .prettierrc.json

```json
{
  "trailingComma": "es5",
  "tabWidth": 4,
  "semi": true,
  "singleQuote": false
}
```

- add script in package.json
To check if some file had a bad formmating for example.
```json
{
  "lint": "prettier --check ."
}
```

- Go further, add a github action to forbid merge if files are not well formatted

Add a github action via  adding this file in project root `.github/workflows/frontend-test.yml`

```yml
name: Test Frontend

on:
  pull_request:

jobs:
  test:

    runs-on: ubuntu-latest
    env:
      WORKING_DIRECTORY: ./frontend/my-project

    steps:
      - uses: actions/checkout@v3
      - name: Install Node
        uses: actions/setup-node@v3
        with:
          node-version: 18
          cache: 'npm'
          cache-dependency-path: '${{ env.WORKING_DIRECTORY }}/package-lock.json'
      - name: Install Application
        run: npm ci
        working-directory: ${{ env.WORKING_DIRECTORY }}
      - name: Lint
        run: npm run lint
        working-directory: ${{ env.WORKING_DIRECTORY }}
      - name: Build
        run: npm run build
        working-directory: ${{ env.WORKING_DIRECTORY }}
```

It means you now have to format all files
`npx prettier --write .`

We can add a command in package.json to enhance use, or automatically format by configurate IDE to format automatically on save or go further by lint staged files with a pre-commit hook

# Adding lint-staged package

# More to come

- adding .editorconfig to fix some rules
- adding eslint configuration to prevent bugs and fix errors like unused variables or packages imported but not used


https://delicious-insights.com/fr/articles-et-tutos/git-hooks-et-lint-staged/