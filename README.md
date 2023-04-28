# eslintrc
This projects maintains a curated list of eslint rules for typescript projects.
Rule selection is subject to practicality, personal taste and inter-operability with built-in typescript rules.

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

Add the following ```devDependencies``` to the ```package.json``` file. The specific versions will be regularly updated once possible rule changes/additions/deprecations have been verified and integrated into the list. 
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
```javascript
// The rules below are consistent with the list of enabled eslint rules.
// To create a new tsconfig.json file execute the command 'tsc --init'.

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
