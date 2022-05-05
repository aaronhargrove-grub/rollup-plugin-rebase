# Rollup Rebase

Forked from [rollup-plugin-rebase](https://www.npmjs.com/package/rollup-plugin-rebase). This just adds two small options I needed. Please use the original author's version.

The Rollup Rebase Plugin copies static assets as required from your JavaScript code to the destination folder and adjusts the references in there to point to the new location. It also respects assets referenced from your CSS/SCSS files.

## Features

- Copies over asset files references from JavaScript into the given output folder.
- Adjust asset references in the output JavaScript files to map to the relative new location.
- Transforms CSS files to inline all includes from `@import` via [PostCSS Import](https://github.com/postcss/postcss-import) into the origin files.
- Detects and processes assets referenced from both, JavaScript and CSS.
- Renames all assets based on their hash (XXHash + Base62) so that conflicts are automatically eliminated while producing a flat output structure.
- Supports _normal_ CSS, but also [SugarSS](https://github.com/postcss/sugarss), [SCSS](https://github.com/postcss/postcss-scss) and [Sass](https://github.com/aleshaoleg/postcss-sass) via the standard PostCSS parser plugins.

## Installation

```console
$ npm install --save-dev rollup-plugin-rebase
```

or

```console
$ yarn add --dev rollup-plugin-rebase
```

## Usage

You can configure Rollup Rebase as part of your Rollup configuration. This can be either done in a `rollup.config.js` or by scripting using the Rollup API:

```js
import { rollup } from "rollup"
import rebasePlugin from "rollup-plugin-rebase"

async function config() {
  const bundle = await rollup({
    input: "./src/index.js",
    plugins: [rebasePlugin()]
  })

  await bundle.write({
    dest: "./lib/index.js"
  })
}

config()
```

### Options (all optional)

- `assetFolder`: When set assets are placed inside a sub folder with that name.
- `keepName`: If `true`, generated filenames will be `${filename}~${hash}.${ext}` instead of just `${hash}.${ext}`
- `verbose`: If `true`, increases log level
- `include`: Standard include option for rollup plugins.
- `exclude`: Standard exclude option for rollup plugins.
- `skipHash`: Skips the step that adds a hash to the file names. Requires `keepName`.
- `includeScripts`: Enabled script files to be rebased, as they are ignored by default.

## Copyright

Forked from:

[rollup-plugin-rebase](https://www.npmjs.com/package/rollup-plugin-rebase)

Copyright 2016-2022<br/>[Sebastian Software GmbH](http://www.sebastian-software.de)
