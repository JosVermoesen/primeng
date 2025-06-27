# primeng 19

## Good practices: if you prefere modules do use lazy loading (mostly for large apps or before Angular 17)

- Generate modules ex. a help module: `ng generate module modules/help --route help --module app.module`
- Generate modules ex. a contact module: `ng generate module modules/contact --route contact --module app.module`
- Generate EuropAssistance offers module: `ng generate module modules/insurances/ins-offers/ea-offers --route ea-offers --module modules/insurances/ins-offers/ins-offers.module`

## Updating to latest Angular 19

This app is now on Angular 19.

### update app to latest Angular 19

`ng update @angular/cli@19 @angular/core@19`

### update from older Angular versions to the latest

Follow the instructions in the [Angular Update Guide](https://update.angular.io/) to fix your app.

Please note that then the --force flag is mostly required to be sure that the update command runs even if there are dependency conflicts for thirth party libraries.

### standalone components

You can switch older Angular programs to standalone with `ng generate @angular/core:standalone`

#### npm outdated

In terminal use `npm outdated` to see what packages are requiring updates and what their current and wanted versions are.

This will also show you which packages are deprecated.

If you want to update a package to a version newer than what is specified in your package.json, you can do so by running npm update [package-name]@[version-number].

### vulnerabilities

In terminal use `npm audit fix` to automatically install compatible updates to vulnerable dependencies.

You can first run `npm audit` to see vulnerabilities in your project for one or more packages.

Run `npm ls [package-name]` to see which packages depend on the vulnerable package.

### avoiding npm install errors

If you get dependencies errors when running `npm install`, you can try to override the error by adding the following to your package.json:

for example:

```json
"ng2-file-upload": "^5.0.0"
```

can be overridden with:

```json
"overrides": {
    "ng2-file-upload": {
      "@angular/common": "$@angular/common",
      "@angular/core": "$@angular/core"
    }    
  }
```

### Use latest global Angular CLI

`npm i -g @angular/cli`
