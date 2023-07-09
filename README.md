## Create Chrome Extensions with React


### 00 - Getting Started
- Get the `manifest.json` file from the [chrome extension documentation](https://developer.chrome.com/docs/extensions/mv3/manifest/) and add it to the public folder.

Now you can load the extension in google chrome by following the steps below:
- Go to `chrome://extensions/` in your browser.
- Click `Load unpacked`.
- then select the `build` folder.

### 01 - Added Description & Icons
`manifest_version`, `name`, `version` are only the required keys to add into the `manifest.json` file. But we can add more keys to make our extension more useful. For example, we can add `description` and `icons` keys to the `manifest.json` file.


make sure to add the icons in the `public` folder and contains the following sizes:
- 16x16
- 48x48
- 128x128

### 02 - Added **React.js** to the project.
In this example I'll go with `npm`

Initialize the project
```bash
npm init -y
```

Add React.js to the project
```bash
npm i react react-dom
```

### 03 - Added **Webpack** to the project.

Install Webpack
```bash
npm i webpack webpack-cli --save-dev
```

Create a `webpack.config.js` file in the root directory and add the following code:
```js
module.exports = {
    mode: 'developer',
    entry: './src/index.tsx',
    module: {
        rules: [
            {
                use: 'ts-loader',
                test: /\.tsx$/,
                exclude: /node_modules/
            }
        ]
    },
    resolve : {
        extensions: ['.tsx', '.ts', '.js']
    }
    output: {
        filename: './dist/index.js'
    }
}
```

- `mode` is the mode of the webpack. It can be `development` or `production`.
- `entry` is the entry point of the project. (good to know: you can add multiple entry points)
- `module` is the module of the webpack.
- `output` is the output of the webpack.

Check if you have typescript installed
```bash
tsc -v
```

If you don't have typescript installed, install it
```bash
npm i typescript --save-dev
```

Now what we need is a loader.
```bash
npm i ts-loader --save-dev
```

Add run command to the `package.json` file
```json
"scripts": {
    "build": "webpack"
}
```

Create a `tsconfig.json` file
```json
 {
     "compilerOptions": {
         "jsx": "react",
         "module": "es6",
         "target": "es6",
         "moduleResolution": "node",
         "esModuleInterop": true,
     },
     "include": ["src/**/*.ts", "src/**/*.tsx"],
     "exclude": ["node_modules"],
 }
```


