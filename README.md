#less-precompiler
The less-precompiler allows you to author your stylesheets with the CSS superset of
[LESS](http://lesscss.org/#docs). It supports `@variables`, `.mixins()` and lots of
other really useful stuff. The less files will get compiled and _attached to your 
couchapp on every build and can even be compressed.

###Install
Add `less-precompiler` to your dependencies section in `kanso.json`.

```javascript
  ...
  "dependencies": {
    "less-precompiler": null,
    ...
  }
```

> run `kanso install` to fetch the package

###Configure
To tell the precompiler which files to transform, add the section `less`,
and in a key called `compile`, list the files you want to process.

```javascript
  ...
  "less": {
    "compile": [ "css/style.less", ... ]
  }
  ...
  "dependencies": {
    "less-precompiler": null,
    ...
  }

```

> Running `kanso push` will compile the file `css/style.less` to 
`css/style.css` and upload it to `_attachments/css/style.css`.

###Compression

To enable compression of the output, add the `compress` flag and set it to `true`.

```javascript
  ...
  "less": {
    "compile": [ ... ],
    "compress": true
  }
```