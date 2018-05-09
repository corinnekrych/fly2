This project is a simple example of how to use [patternfly-react] and [patternfly css] with a react project using [Create React App](https://github.com/facebookincubator/create-react-app) cli.

## How to create this app

* Scaffold with [Create React App](https://github.com/facebookincubator/create-react-app)
```
npx create-react-app fly2
cd fly2
npm install —save-dev node-sass-chokidar
npm install --save patternfly-react
npm install --save patternfly  
npm install --save bootstrap-sass
npm install --save font-awesome-sass
npm install --save-dev npm-run-all 
```

* In `package.json` in `scripts` section:
```
"build-css": "node-sass-chokidar --include-path ./src --include-path ./node_modules --include-path node_modules/patternfly-react/dist/sass --include-path node_modules/patternfly/dist/sass --include-path node_modules/bootstrap-sass/assets/stylesheets --include-path node_modules/font-awesome-sass/assets/stylesheets src/ -o src/",
"watch-css": "npm run build-css && node-sass-chokidar --include-path ./src --include-path ./node_modules src/ -o src/ --watch --recursive",
"start-js": "react-scripts start",
"start": "npm-run-all -p watch-css start-js",
"build-js": "react-scripts build",
"build": "npm-run-all build-css build-js",
```
* Rename App.css => App.scss

* Run:
```
npm install
npm run build
Failed to compile.
Module not found: Error: You attempted to import ../fonts/OpenSans-Light-webfont.eot which falls outside of the project src/ directory. Relative imports outside of src/ are not supported. You can either move it inside src/, or add a symlink to it from project's node_modules/.```
```
