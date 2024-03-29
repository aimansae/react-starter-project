# React + TypeScript + Vite Starter Project

This is a starter project for react.
Please find the Guidelines for the project:

## Requirements

1. Use Vite (as a bundler)
2. Use Typescript
3. Configure TS path aliases
4. Configure [Jest](https://kulshekhar.github.io/ts-jest/docs/getting-started/installation) & React testing library and write a single or multiple unit tests. They all have to be passing! (For example, you can test if a text is being rendered in a component.)
   No specific functionality is necessary (like headings, buttons, pages, etc.) - at the end, it’s just a starter.
   Do not add any styling libraries. - We want to have a flexible starter!
5. Use prettier and configure your IDE to reformat the code on save.

### Additional requirements

1. Create a Github repository.
2. Commit your changes frequently. (For example - you’ve just initialised the project - commit “Initial commit”. You’ve configured the tsconfig.json, another commit) Keep them small but meaningful.
   Adjust your README.md to explain your project better.

**Time limit**: 4 hours

## Getting Started

1. **Install Vite**:

   To install [Vite](https://vitejs.dev/guide/) as a bundler:

   ```bash
   npm create vite@latest
   ```

Follow the indications on the terminal, select a name, React as Framework, Typescript as Variant.

**Run the Project:**

After creating the project, navigate to the project folder and install dependencies:

```
  cd (folder name) react-starter
  npm i
  npm run dev
```

3. To configure Ts path aliases in tsconfig.json add :

```
"baseUrl": "./",
"paths": {
"@app/_": ["src/_"],
"@shared/_": ["src/shared/_"]
}
```

Update Module Resolution (For Node.js):

npm install tsconfig-paths --save-dev

4. To configure Jest and React testing library:

   npm install --save-dev jest typescript ts-jest @types/jest

   npm install --save-dev jest @testing-library/react @testing-library/jest-dom

   npm install --save-dev jest-environment-jsdom

   npx ts-jest config:init

Configure jest.config.cjs file:

@typescript-eslint/no-var-requires
const { defaults } = require('ts-jest/presets/index.js');

    module.exports = {
      ...defaults,
      testEnvironment: 'jsdom',
    };

Created a component, a Text.test.tsx file to test if the heading is being rendered

5. To setup Eslint and Prettier please find the guide [here](https://dev.to/knowankit/setup-eslint-and-prettier-in-react-app-357b)

## Troubleshooting

- While running npm test, encountered error: " "Missing script" : 'test'"

Fixed: in package.json added:

```
  "scripts": {
  "test": "jest"
}
```

- TypeError: expect(...).toHaveTextContent is not a function

- After running npm test encountered warning: ts-jest[config] (WARN) message TS151001: If you have issues related to imports, you should consider setting `esModuleInterop` to `true` in your TypeScript configuration file (usually `tsconfig.json`). See https://blogs.msdn.microsoft.com/typescript/2018/01/31/announcing-typescript-2-7/#easier-ecmascript-module-interoperability for more information.

Fixed by adding in tsconfig.json: "esModuleInterop": true,

- TS not recognising the existence of the .toBeInTheDocument() method. In tsconfig.json add, in COmpilerOptions add:
  “types”: [“node”, “jest”, “@testing-library/jest-dom”], in “compilerOptions

- To disable and make ESLint ignore some of the files in your repo. In ESLint config add:

  ignorePatterns: ["webpack.config.js", ".eslintrc.js", "jest.config.js", "babel.config.js"],

## Github setup

1. Create a local folder and connect it to [Github](https://github.com/)

In terminal Terminal type :

git init
git add .
git commit -m ‘First commit’

2. Open github and create new reposotory

Copy the link and in terminal add:

git remote add origin (paste the link to the Github repo here)
git push origin master

If needed Enter credentials to connect the IDE to Gthub

Resources found on [Youtube](https://www.youtube.com/watch?v=vbQ2bYHxxEA)
