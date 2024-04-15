## Setting up Linters & Husky pre-commit
## ESLint config based on AirBnb JS/TS

1. ### Do not install/enable husky pre-commit until all ESLint errors are resolved
2. Installation of extensions (first, insert dependencies into package.json):
   - `npm install`
   - Install the necessary dev dependencies from the package.json file of the corresponding project (react-ts / vue-js / ....)
3. Copy to your project:
   - .eslintrc.json from the corresponding project into the root folder of your project
   - supplement your package.json with the code from the package.json file of the corresponding project
   - copy the files .prettierrc.json, .stylelintrc.json, .prettierignore, .eslintignore from the folder all-projects-files into the root folder of your project
4. watchers.xml file - a utility for automatic linting of css /scss files
   - in the IDE Webstorm, connect in settings > tools > filewatchers
   - import this file and enable styleint, styleint scss
5. Resolve emerging import errors / necessary dependencies
6. For VSCode, it is necessary to install and enable the prettier, eslint, styleint extensions
7. For VSCode, it is necessary to configure the settings.json file
8. Run the linters: npm run lint, npm run format
9. Analyze errors, if any errors appear that are already very difficult to correct, report in the TG group, we will discuss changing configs > then debugging > launching on live projects
10. After finalizing the configs and resolving all errors, install/enable husky and git hooks and check the functionality of husky pre-commit, it should prevent push if there are ESLint errors:
- `npm i lint-staged --save-dev`
- `npx husky-init && npm install`
- `npx husky add .husky/pre-commit "npx lint-staged"`
- In the husky -> pre-commit folder -> comment out npm test (if you do not have tests in your project)
- Intentionally leave/create one ESLint error to check the functionality of husky

### Config tested on: **react-ts (vite)**


