# Storyblok import and export

A Node.js Script that allows you to export and import a CSV to Storyblok.

<hr>

The Node.js Script checks for column values starting with `http` and downloads the original File into the  `./images/` folder and than uploads it to Storyblok.

## Configuration Options for config.js

```js
module.exports = {
  storyblok: {
    export: {
      previewToken: 'token',         // for export -> Delivery API
      options: {                                  // Content Delivery Parameters
        // starts_with: '/your-folder-slug',      // folder you want to export as CSV,
        version: 'draft',                         // version of content that should be exported
        per_page: 100,                            // 100 is max atm
        page: 10                                   // can be upped as needed.
      }
    }
  }
}
```

## How to use it

### Exporting data from Storyblok as CSV

1. Configure the `previewToken` with the preview token of your space.
2. Leave the `options.starts_with` blank or remove if you dont want to use a specific folder.
3. Define the version of content which should be used `options.version`.
4. You can use any kind of Content Delivery Parameters in `options`.
5. Export will be saved at `/export/<timestamp>.csv`.
6. Execute `npx run export`.


