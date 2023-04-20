# eslintrc
This projects maintains a curated list of eslint rules for typescript projects.
Rules selection subject to practicality and personal taste.

## Install

### git

Add this repository as a git submodule to your root repository:
```bash
# the typescript project is the root repository
git submodule add https://github.com/pfui-bah-kiste/eslintrc.git

# the typescript project is within a subfolder of the root repository, e.g. server
git submodule add https://github.com/pfui-bah-kiste/eslintrc.git server/eslintrc
```

### vscode

Install extension:
```ESLint (v2.4.0)```

## Configure

Add the following ```devDependencies``` to the ```package.json``` file:
```json
"@typescript-eslint/eslint-plugin": "5.58.0"
"@typescript-eslint/parser": "5.58.0"
"eslint": "8.38.0"
"eslint-plugin-jsdoc": "41.1.1"
```


In the root of the typescript project,

* create the ```.eslintrc.json``` file with the following content:
```json
{
    "root": true,
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

* append the following content to the ```tsconfig.json``` file:
```json
// The rules below are consistent
// with the enabled eslint rules.

"compilerOptions": {
    // [...]

    /* Type Checking */
    "strict": true,
    "noImplicitAny": true,
    "strictNullChecks": true,
    "strictFunctionTypes": true,
    "strictBindCallApply": true,
    "strictPropertyInitialization": true,
    "noImplicitThis": true,
    // "useUnknownInCatchVariables": true,
    "alwaysStrict": true,
    "noUnusedLocals": true,
    // "noUnusedParameters": true,
    "exactOptionalPropertyTypes": true,
    "noImplicitReturns": true,
    "noFallthroughCasesInSwitch": true,
    // "noUncheckedIndexedAccess": true,
    "noImplicitOverride": true,
    "noPropertyAccessFromIndexSignature": true,
    // "allowUnusedLabels": true,
    // "allowUnreachableCode": true,
}
```
