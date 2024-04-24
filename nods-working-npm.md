# Working with npm



## npm vs. npx

### npm

- npm is the Node Package Manager used for:
  - Installing, managing, and publishing packages in Node.js projects.
  - Running scripts defined in the `package.json` file.
- Example usage:
  - `npm install <package-name>` to install a package.
  - `npm start` to run the start script defined in `package.json`.

### npx

- npx is a package runner tool that comes with npm 5.2+ versions.
- It is used for:
  - Executing Node packages without installing them globally.
  - Running commands from packages in the npm registry or executing binaries from locally installed packages.
- Example usage:
  - `npx <command>` to run a command from a package.
  - `npx create-react-app my-app` to create a new React application without installing `create-react-app` globally.

