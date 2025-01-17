![UI5 logo](/docs/images/Designer.png)
[![CI](https://github.com/SAP-samples/ui5-webcomponents-sample-react/actions/workflows/ci.yml/badge.svg)](https://github.com/SAP-samples/ui5-webcomponents-sample-react/actions/workflows/ci.yml)
[![REUSE status](https://api.reuse.software/badge/github.com/SAP-samples/ui5-webcomponents-sample-react)](https://api.reuse.software/info/github.com/SAP-samples/ui5-webcomponents-sample-react)

# UI5 Web Components React Sample Application


[React](https://reactjs.org/) sample application to demonstrate the usage of the [UI5 Web Components](https://github.com/SAP/ui5-webcomponents). It shows how to bind properties, to subscribe to events, using nested components and the bootstrapped React build.
 
This project was bootstrapped with [Create React App](https://github.com/facebook/create-react-app).
 
## Prerequisites
- [Node.js](https://nodejs.org/) (**version 8.5 or higher** ⚠️)
- [Yarn](https://yarnpkg.com/en/) (Optional usage of yarn)

## Getting started
1. [Clone this repository](https://help.github.com/articles/cloning-a-repository/) using the [GitHub Command line tool](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git) and navigate into the downloaded directory.
    ```sh
    git clone https://github.com/SAP-samples/ui5-webcomponents-sample-react.git
    cd ui5-webcomponents-sample-react
    ```
2. Install all dependencies
    ```sh
    npm install
    ```

3.  Start a local server and run the application. (The running application can be found here: http://localhost:3000)
    ```sh
    npm start
    ```

## Noteworthy
 
### Consume UI5 Web Components
Import the desired component(s) in your app to define the UI5 Web Component.
 
For example, to use ```ui5-button``` you need to import it:
 
```js
import "@ui5/webcomponents/dist/Button"; // loads ui5-button
```
 
Then, you can use the custom element in an HTML page:
 
```html
<ui5-button>Hello world!</ui5-button>
```

## Browser support

Currently Chrome, Safari, Firefox and Edge (Chromium-based) support Web Components natively.


## Configure React Build
When UI5 Web Components are used they include all of their translation files and CLDR data files in the application bundle.
In order to decrease the bundle size of the application a custom Webpack configuration should be provided.
(This configuration is already done for this project, so you will NOT be able to run ``` npm run eject```, because it is
one time operation, which can NOT be reverted.)

1. Eject the react build with ```npm run eject```
2. Open ```config/webpack.config.js``` file and add the following lines before the last loader:
```js
{
  test: [/cldr\/.*\.json$/, /i18n\/.*\.json$/],
  loader: 'file-loader',
  options: {
    name: 'static/media/[name].[hash:8].[ext]',
  },
  type: 'javascript/auto'
},
// "file" loader makes sure those assets get served by WebpackDevServer.
// When you `import` an asset, you get its (virtual) filename.
// In production, they would get copied to the `build` folder.
// This loader doesn't use a "test" so it will catch all modules
// that fall through the other loaders.
```

### Where is the npm package?
- [UI5 Web Components](https://www.npmjs.com/package/@ui5/webcomponents)

## Limitations
No limitations known.

## Known Issues
No major bugs known.

## Support
We welcome all comments, suggestions, questions, and bug reports. Please follow our [Support Guidelines](https://github.com/SAP/ui5-webcomponents/blob/main/SUPPORT.md#-content) on how to report an issue, or chat with us in the `#webcomponents` channel of the [OpenUI5 Community Slack](https://ui5-slack-invite.cfapps.eu10.hana.ondemand.com/).

## Contribute to UI5 Web Components
Please check our [Contribution Guidelines](https://github.com/SAP/ui5-webcomponents/blob/main/CONTRIBUTING.md).
