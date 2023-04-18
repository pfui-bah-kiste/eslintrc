# eslintrc
This projects maintains a curated list of eslint rules for typescript projects.
Rules selection subject to practicality and personal taste.

## Usage

### Install

Add this repository as a git submodule to your project:
```bash
git submodule add https://github.com/pfui-bah-kiste/eslintrc.git

444 Remove the fllowing line is unsafe
```

### Configure

Add the following dev dependencies to your package.json file:
- ```"@typescript-eslint/eslint-plugin": "5.58.0"```
- ```"@typescript-eslint/parser": "5.58.0"```
- ```"eslint": "8.38.0"```
- ```"eslint-plugin-jsdoc": "41.1.1"```

Create an ```.eslintrc.json``` file in the root of your typescript project with the following content:
```json
{
    "root": true,
    "env": {
        "browser": true,
        "node": true,
        "es6": true
    },
    "parser": "@typescript-eslint/parser",
    "parserOptions": {
        "project": "tsconfig.json"
    },
    "plugins": [
        "@typescript-eslint",
        "eslint-plugin-jsdoc"
    ],
    "extends": [
        "./eslintrc/.eslintrc.json"
    ]
}
```