# Reconbot's JSDoc3 Theme

A clean, responsive documentation template theme for JSDoc 3, based on [postman-jsdoc-theme](https://github.com/postmanlabs/postman-jsdoc-theme)

## Install

```bash
$ npm install --save-dev @reconbot/jsdoc-theme
```

## Usage

Clone repository to your designated `jsdoc` template directory, then:

```bash
$ jsdoc entry-file.js -t path/to/postman-jsdoc-theme
```

Optionally, provide a package version on the command line, which will be rendered into the final documentation
```bash
$ jsdoc entry-file.js -t path/to/postman-jsdoc-theme --query 'pkgVersion=2.3.0'
```

### Node.js Dependency

In your projects `package.json` file add a generate script:

```json
"script": {
  "generate-docs": "node_modules/.bin/jsdoc --configure .jsdoc.json --verbose"
}
```

In your `.jsdoc.json` file, add a template option.

```json
"opts": {
  "template": "node_modules/postman-jsdoc-theme"
}
```

### Example JSDoc Config

```json
{
    "tags": {
        "allowUnknownTags": true,
        "dictionaries": ["jsdoc"]
    },
    "source": {
        "include": ["lib", "package.json", "README.md"],
        "includePattern": ".js$",
        "excludePattern": "(node_modules/|docs)"
    },
    "plugins": [
        "plugins/markdown"
    ],
    "templates": {
        "cleverLinks": true,
        "monospaceLinks": true
    },
    "opts": {
        "destination": "./docs/",
        "encoding": "utf8",
        "private": true,
        "recurse": true,
        "template": "./node_modules/postman-jsdoc-theme"
    },
    "reconbot": {
        "github":"https://github.com/reconbot/jsdoc-theme"
    }
}
```

## License

Licensed under the MIT license.
