# Todo

This project was generated with [Angular CLI](https://github.com/angular/angular-cli) version 10.1.7.

## Steps
### Create Scaffolding
ng new todo
### Install jest
npm install jest @types/jest jest-preset-angular --save-dev
### Uninstall Karma
npm uninstall jasmine @types/jasmine
npm uninstall karma karma-chrome-launcher karma-coverage-istanbul-reporter karma-jasmine karma-jasmine-html-reporter 
### Remove test from angular.json
### Remove karma.conf.js and src/test.ts files
### Create setupJest.ts file at root folder
    import 'jest-preset-angular';
### Modify tsconfig.spec.json
    {
  "extends": "./tsconfig.json",
  "compilerOptions": {
    "outDir": "./out-tsc/spec",
    "types": [
      "jest",
      "node"
    ]
  },
  "files": [
    "src/test.ts",
    "src/polyfills.ts"
  ],
  "include": [
    "src/**/*.spec.ts",
    "src/**/*.d.ts"
  ]
}

### Modify package.json file
    "test": "jest",
    "test:coverage": "jest --coverage",
### Add Jest configuration to the end of this file:
    "jest": {
    "preset": "jest-preset-angular",
    "setupFilesAfterEnv": [
      "<rootDir>/setupJest.ts"
    ],
    "testPathIgnorePatterns": [
      "<rootDir>/node_modules/",
      "<rootDir>/dist/",
      "<rootDir>/src/test.ts"
    ],
    "globals": {
      "ts-jest": {
        "tsConfig": "<rootDir>/tsconfig.spec.json",
        "stringifyContentPathRegex": "\\.html$"
      }
    }
}




2. followed : https://dev.to/alfredoperez/angular-10-setting-up-jest-2m0l
3. Not opting jest reasons : https://itnext.io/how-to-use-jest-in-angular-aka-make-unit-testing-great-again-e4be2d2e92d1



