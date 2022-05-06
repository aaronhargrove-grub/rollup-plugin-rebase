# Rollup Rebase

Forked from [rollup-plugin-rebase](https://www.npmjs.com/package/rollup-plugin-rebase). This just adds a few small options I needed. Please use the original author's version, as this is intended for a specific project's needs, and will change with the needs of that project.

### Options (all optional)

- `assetFolder`: When set assets are placed inside a sub folder with that name.
- `keepName`: If `true`, generated filenames will be `${filename}~${hash}.${ext}` instead of just `${hash}.${ext}`
- `verbose`: If `true`, increases log level
- `include`: Standard include option for rollup plugins.
- `exclude`: Standard exclude option for rollup plugins.
- `skipHash`: Skips the step that adds a hash to the file names. Requires `keepName`.
- `includeScripts`: Enabled script files to be rebased, as they are ignored by default.
- `flatten`: Should the dir structure be flattened. Defaults to `true`
  - NOTE: If flatten is `false`, it will include the full folder structure from root by default.
- `buildFolderStructureFrom`: If you're rebasing a single folder, have flatten set to `false`, and don't want the full path to be copied, specify the path of the folder (from root) that you want excluded from the final path.
  - Example. include is set to `'src/resources/images/**'`. This option could be `'/src/resources/images/'`

## Copyright

Forked from:

[rollup-plugin-rebase](https://www.npmjs.com/package/rollup-plugin-rebase)

Copyright 2016-2022<br/>[Sebastian Software GmbH](http://www.sebastian-software.de)
