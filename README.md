# AngularUniversalCrudStarter

This project was generated with [Angular CLI](https://github.com/angular/angular-cli) version 13.3.5.

## Development server

Run `ng serve` for a dev server. Navigate to `http://localhost:4200/`. The application will automatically reload if you change any of the source files.

## Code scaffolding

Run `ng generate component component-name` to generate a new component. You can also use `ng generate directive|pipe|service|class|guard|interface|enum|module`.

## Build

Run `ng build` to build the project. The build artifacts will be stored in the `dist/` directory.

## Running unit tests

Run `ng test` to execute the unit tests via [Karma](https://karma-runner.github.io).

## Running end-to-end tests

Run `ng e2e` to execute the end-to-end tests via a platform of your choice. To use this command, you need to first add a package that implements end-to-end testing capabilities.

## Further help

To get more help on the Angular CLI use `ng help` or go check out the [Angular CLI Overview and Command Reference](https://angular.io/cli) page.


## Getting started with Angular Universal
```
$ ng add @nguniversal/express-engine
```

### Run Server-Side
```
$ npm run dev:ssr
```

### Configure ESLint and Prettier
```
$ npm install prettier eslint-plugin-prettier eslint-config-prettier --save-dev
```

create file .prettierrc.json and add :
```
{
  "singleQuote": true,
  "trailingComma": "none",
  "endOfLine": "auto"
}
```

Create file .eslintrc.json and add :

```
{
  "root": true,
  "ignorePatterns": [
    "projects/**/*"
  ],
  "overrides": [
    {
      "files": [
        "*.ts"
      ],
      "parserOptions": {
        "project": [
          "tsconfig.json",
          "e2e/tsconfig.json"
        ],
        "createDefaultProgram": true
      },
      "extends": [
        "eslint:recommended",
        "plugin:@angular-eslint/recommended",
        "plugin:@angular-eslint/template/process-inline-templates",
        "plugin:prettier/recommended"
      ],
      "rules": {
        "@angular-eslint/component-selector": [
          "error",
          {
            "prefix": "app",
            "style": "kebab-case",
            "type": "element"
          }
        ],
        "@angular-eslint/directive-selector": [
          "error",
          {
            "prefix": "app",
            "style": "camelCase",
            "type": "attribute"
          }
        ],
        "sort-imports": [
          "error",
          {
            "ignoreCase": false,
            "ignoreDeclarationSort": false,
            "ignoreMemberSort": false,
            "memberSyntaxSortOrder": ["none", "all", "multiple", "single"],
            "allowSeparatedGroups": false
          }
        ]
      }
    },
    {
      "files": [
        "*.html"
      ],
      "extends": [
        "plugin:@angular-eslint/template/recommended"
      ],
      "rules": {}
    }
  ]
}
```

Create .eslintignore and add :

```
package.json
package-lock.json
dist
e2e/**
karma.conf.js
commitlint.config.js
```

Update package.json

```
"scripts": {
    ...
    "lint": "npx eslint 'src/**/*.{js,jsx,ts,tsx,html,css,scss}' --quiet --fix",
    "format": "npx prettier 'src/**/*.{js,jsx,ts,tsx,html,css,scss}' --write",
}
```

Configure Husky
```
$ npx mrm@2 lint-staged
```

Run formatter
```
$ npm run format && npm run lint
```