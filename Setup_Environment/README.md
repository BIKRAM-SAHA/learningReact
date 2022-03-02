[Back to Content](../README.md)


## Pre-requisite for ReactJS
- NodeJS and NPM
- React and React DOM
- Webpack
- Babel

## Ways to install ReactJS
There are two ways to set up an environment for successful ReactJS application. They are given below.

<details>
<summary> Using the npm command</summary>

- Install NodeJS and NPM
- Install React and React DOM
    - Create a `project root folder` with the name `<custom reactApp name>`
    - Create a package.json file
    To create any module, package.json is required to be generated in the project folder. To do so run the following inside the `project root folder`:
        ```
        npm init -y
        ```
    - Now install react and its DOM packages using
        ```
        npm install react react-dom --save
        ```
- Install Webpack
    - Webpack is used for module packaging, development, and production pipeline automation. We will use `webpack-dev-server` during development, `webpack` to create production builds, and `webpack CLI` provides a set of commands. Webpack compiles these into a single file(bundle).
    - run:
        ```
        npm install webpack webpack-dev-server webpack-cli --save
        ```
- Install Babel
    - Babel is a JavaScript compiler and transpiler used to convert one source code to others. It compiles React JSX and ES6 to ES5 JavaScript which can be run on all browsers. We need `babel-loader` for JSX file types, `babel-preset-react` makes your browser update automatically when any changes occur to your code without losing the current state of the app. ES6 support requires `babel-preset-env` Babel preset
    - run:
        ```
        npm install babel-core babel-loader babel-preset-env babel-preset-react babel-webpack-plugin --save-dev
        ```
- Create Files
    - To complete the installation process, you need to add the following files in your project folder. These files are `index.html`, `App.js`, `main.js`, `webpack.config.js` and `.babelrc`.
- Set Compiler, Loader, and Server for React Application
    - Configure webpack
        - You can configure webpack in the `webpack.config.js` file by adding the following code.
        - It defines your app entry point, build output and the extension which will resolve automatically. It also set the development server to `8080` port. It defines the loaders for processing various file types used within your app and wrap up by adding plugins needed during our development.
        - webpack.config.json:
            ```javascript
            const path = require('path');  
            const HtmlWebpackPlugin = require('html-webpack-plugin');  
            
            module.exports = {  
            entry: './main.js',  
            output: {  
                path: path.join(__dirname, '/bundle'),  
                filename: 'index_bundle.js'  
            },  
            devServer: {  
                inline: true,  
                port: 8080  
            },  
            module: {  
                rules: [  
                    {  
                        test: /\.jsx?$/,  
                        exclude: /node_modules/,  
                    use: {  
                        loader: "babel-loader",  
                        }  
                    }  
                ]  
            },  
            plugins:[  
                new HtmlWebpackPlugin({  
                    template: './index.html'  
                })  
            ]  
            }
            ```
        - Now, open the `package.json` file and delete "`test`" "`echo \" Error: no test specified\" && exit 1`" inside "`scripts`" object, then add the start and build commands instead. It is because we will not perform any testing in this app.
            ```json
            {  
            "name": "reactApp",  
            "version": "1.0.0",  
            "description": "",  
            "main": "index.js",  
            "scripts": {  
                "start": "webpack-dev-server --mode development --open --hot",  
                "build": "webpack --mode production"  
            },  
            "keywords": [],  
            "author": "",  
            "license": "ISC",  
            "dependencies": {  
                "react": "^16.8.6",  
                "react-dom": "^16.8.6",  
                "webpack-cli": "^3.3.1",  
                "webpack-dev-server": "^3.3.1"  
            },  
            "devDependencies": {  
                "@babel/core": "^7.4.3",  
                "@babel/preset-env": "^7.4.3",  
                "@babel/preset-react": "^7.0.0",  
                "babel-core": "^6.26.3",  
                "babel-loader": "^8.0.5",  
                "babel-preset-env": "^1.7.0",  
                "babel-preset-react": "^6.24.1",  
                "html-webpack-plugin": "^3.2.0",  
                "webpack": "^4.30.0"  
            }  
            }
            ```
    - HTML webpack template for index.html
        - We can add a custom template to generate index.html using the HtmlWeb-packPlugin plugin. This enables us to add a viewport tag to support mobile responsive scaling of our app. It also set the div id = "app" as a root element for your app and adding the index_bundle.js script, which is our bundled app file.
            ```html
            <!DOCTYPE html>  
            <html lang = "en">  
            <head>  
                <meta charset = "UTF-8">  
                <title>React App</title>  
            </head>  
            <body>  
                <div id = "app"></div>  
                <script src = 'index_bundle.js'></script>  
            </body>  
            </html>  
            ```
    - Setting up App.jsx and main.js
        - This is the first React component, i.e. app entry point. It will render Hello World.
        - App.js
            ```java
            import React, { Component } from 'react';  
            class App extends Component{  
            render(){  
                return(  
                    <div>  
                        <h1>Hello World</h1>  
                    </div>  
                );  
            }  
            }  
            export default App;
            ```
            Now, import this component and render it to your root App element so that you can see it in the browser.
        - Main.js
            ```java
            import React from 'react';  
            import ReactDOM from 'react-dom';  
            import App from './App.js';  
            
            ReactDOM.render(<App />, document.getElementById('app'));
            ```
    - Create .babelrc file
        - .babelrc
            ```java
            {  
            "presets":[  
            "@babel/preset-env", "@babel/preset-react"]  
            }
            ```
    - Running the Server
        ```
        npm start
        ```
        It will start the server at the shown port number which can be open in browser.
    - Generate the Bundle
        Bundling is the process of following imported files and merging them into a single file: a "bundle". This bundle can then be included on a webpage to load an entire app at once. To generate this, you need to run the build command
        ```
         npm run build 
        ```
    
</details>

<details>
<summary> Using the create-react-app command</summary>

'create-react-app' is a tool maintained by Facebook which can be used if you do not want to manually deal with transpiling tools like webpack and babel.

- Install NodeJS and NPM
- Install React using create-react-app
    - run:
        ```
        npm install -g create-react-app  
        ```
- Create a new React project
    - run:
        ```
        create-react-app <react-project-name>
        ```
- NOTE: or you can use npx (a package running tool), instead of above two commands, which will install the react and create a new project with the name jtp-reactapp.
    - run:
        ```
        npx create-react-app <react-project-name>
        ```
- start work inside `src` folder
    - App.js
        ```javascript
        import React from 'react';  
        import logo from './logo.svg';  
        import './App.css';  
        
        function App() {  
        return (  
            <div className="App">  
            <header className="App-header">  
                <img src={logo} className="App-logo" alt="logo" />  
                <p>  
                Welcome To JavaTpoint.  
        
            <p>To get started, edit src/App.js and save to reload.</p>  
                </p>  
                <a  
                className="App-link"  
                href="https://reactjs.org"  
                target="_blank"  
                rel="noopener noreferrer"  
                >  
                Learn React  
                </a>  
            </header>  
            </div>  
        );  
        }  

        export default App;  
        ```
- Running the Server
    - run:
        ```
        cd <react-project-name>
        npm start
        ```
    - It will show the port number which we need to open in the browser.
</details>

[Previous](../Introduction/README.md)
<br>

[Next](../Create_React_App/README.md)
