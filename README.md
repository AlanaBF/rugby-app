# RugbyApp

This project was generated using [Angular CLI](https://github.com/angular/angular-cli) version 19.1.2.

## Development server

To start a local development server, run:

```bash
ng serve
```

Once the server is running, open your browser and navigate to `http://localhost:4200/`. The application will automatically reload whenever you modify any of the source files.

## Code scaffolding

Angular CLI includes powerful code scaffolding tools. To generate a new component, run:

```bash
ng generate component component-name
```

For a complete list of available schematics (such as `components`, `directives`, or `pipes`), run:

```bash
ng generate --help
```

## Building

To build the project run:

```bash
ng build
```

This will compile your project and store the build artifacts in the `dist/` directory. By default, the production build optimizes your application for performance and speed.

<!-- ## Running unit tests

To execute unit tests with the [Karma](https://karma-runner.github.io) test runner, use the following command:

```bash
ng test 
```-->

## Setting up and Running unit tests

To set up Jest testing in an Angular project, you'll need to follow these steps:

Step 1: Install Jest and required dependencies

Run the following command in your terminal:

```bash
npm install --save-dev jest @types/jest jest-preset-angular
```

This will install Jest, the @types/jest package for TypeScript support, and the jest-preset-angular package, which provides a pre-configured Jest setup for Angular projects.

Step 2: Configure Jest

Create a new file called jest.config.js in the root of your project with the following content:

```javascript
module.exports = {
  preset: 'jest-preset-angular',
  setupFilesAfterEnv: ['<rootDir>/setup-jest.ts'],
  globals: {
    'ts-jest': {
      tsConfig: 'tsconfig.spec.json',
    },
  },
};
```

This configuration tells Jest to use the jest-preset-angular preset and sets up the setupFilesAfterEnv option to run a setup file after the environment has been set up.

Step 3: Create a setup file

Create a new file called setup-jest.ts in the root of your project with the following content:

```typescript
import 'jest-preset-angular/setup-jest';
```

This file imports the setup-jest function from the jest-preset-angular package, which sets up Jest to work with Angular.

Step 4: Update the tsconfig.spec.json file

Update the tsconfig.spec.json file to include the following configuration:

```json
{
  "extends": "./tsconfig.json",
  "compilerOptions": {
    "outDir": "spec"
  }
}
```

This configuration tells the TypeScript compiler to output the compiled files in a spec directory.

Step 5: Update the angular.json file

Update the angular.json file to include the following configuration:

```json
{
  "projects": {
    "your-app": {
      "architect": {
        "test": {
          "builder": "@angular-builders/jest:run",
          "options": {
            "jestConfig": "jest.config.js"
          }
        }
      }
    }
  }
}
```

This configuration tells the Angular CLI to use the @angular-builders/jest builder to run Jest tests.

Step 6: Run Jest tests

Run the following command in your terminal to run Jest tests:

```bash
ng test
```

This will run Jest tests using the configuration you've set up.

## Running end-to-end tests

For end-to-end (e2e) testing, run:

```bash
ng e2e
```

Angular CLI does not come with an end-to-end testing framework by default. You can choose one that suits your needs.

## Additional Resources

For more information on using the Angular CLI, including detailed command references, visit the [Angular CLI Overview and Command Reference](https://angular.dev/tools/cli) page.
