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
npm install react react-dom
```

