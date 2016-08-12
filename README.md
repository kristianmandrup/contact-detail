# Contact Details

Aurelia component with Contact details

## Install

Install the [aurelia-installer](https://github.com/kristianmandrup/aurelia-installer)

`npm i aurelia-installer -g`

### Use the installer

`ai install component kristianmandrup/contact-detail`

This will install the component at:

```bash
src/components
  contact-details.html
  contact-detail.ts
  package.json
  install.json
```

### Post install bundling

To ensure all resource dependencies of the component are integrated with the application, you must bundle the component:

`ai bundle contact-detail`

Bundling of the component  will install all the component dependencies into your app:

- `package.json`
- `install.json`

### package.json

The component `package.json` is a regular npm package descriptor and may contain keywords, description etc. 

Note: We recommend using `ai create` to create your own components with appropriate minimal configuration.

Bundling will take the npm module `dependencies` of the component `package.json` and merged these into the application `package.json` `dependencies` list.

Be sure to run `npm install` after bundling to install dependencies as node modules in your app.

#### install.json

`install.json` can (currently) contain the following entries:

- `bundles`
- `dependencies`
- `typings`

Example:

```json
{
  "bundles": [
    "foundation"
  ],
  "dependencies": [
    "jquery",
    {
      "name": "bootstrap",
      "path": "../node_modules/bootstrap/dist",
      "main": "js/bootstrap.min",
      "deps": ["jquery"],
      "exports": "$",
      "resources": [
        "css/bootstrap.css"
      ]
    }
  ],
  "typings": [
    "nprogress",
    "github:aurelia/dialog"
  ]
}
```

The list of `dependencies` will be merged into the `vendor-bundle.js` `"dependencies"` entry of the project `aurelia.json` config file.

The bundles will look up registered vendor bundle definitions and likewise install these in the project `aurelia.json` config file.

Finally typings will install typings, either by name (via lookup in `typings.json` registry of installer) or by full location, such as `dt~sortablejs`.

In the future we might add support for adding dependencies and source contributions to other bundles, such as `app-bundle.js` (or any custom bundles).

We will also likely add the option to specify plugin dependencies and bundling of these as well ;)

## License

MIT