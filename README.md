# Contact Details

Aurelia component with Contact details

## Install

Use the new component installer

`au install component kristianmandrup/contact-details`

This will install the component at:

```bash
src/components
  contact-details.html
  contact-detail.ts
  package.json
  vendor-bundles.js
```

### Post install

To ensure all resource dependencies of the component are integrated with the application, the following takes place post install.

`package.json` of this component will be merged with and application dependencies.

`vendor-bundles` will be merged into the `vendor-bundle.js` of the project `aurelia.json` config file.

### Component router

Use a Component router to route to a component as per this [PR](https://github.com/aurelia/router/pull/381)

## License

MIT