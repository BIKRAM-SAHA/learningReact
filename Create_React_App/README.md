[Back to Content](../README.md)

# Folder Structure

1. node_modules: It contains the React library and any other third party libraries needed.
2. public: It holds the public assets of the application. It contains the index.html where React will mount the application by default on the <div id="root"></div> element.
3. src: It contains the App.css, App.js, App.test.js, index.css, index.js, and serviceWorker.js files. Here, the App.js file always responsible for displaying the output screen in React.
4. package-lock.json: It is generated automatically for any operations where npm package modifies either the node_modules tree or package.json. It cannot be published. It will be ignored if it finds any other place rather than the top-level package.
5. package.json: It holds various metadata required for the project. It gives information to npm, which allows to identify the project as well as handle the project's dependencies.
README.md: It provides the documentation to read about React topics.


#### Note: 
- create-react-app is set up in such a way that it allows us to import css and images to use in out js


[Previous](../Setup_Environment/README.md)
<br>

[Next](../JSX/README.md)