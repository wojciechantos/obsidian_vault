When Node.js is installed globally:
```bash
node app.js
```

In JS file with shebang declaration, to run it with OS interpreter defined:
```js
#!/usr/bin/node

// js code
```

Above we explicitly pass the absolute path to the interpreter. Not all operating systems have `node` in the bin folder, but all should have `env`. We can pass `node` as parameter to tell OS to run `env` with it:
```js
#!/usr/bin/env node

// js code
```

To use a shebang, it needs to have executable permission:
```bash
chmod u+x app.js
```

### Pass string as argument to `node` instead of file path

A string can be passed as argument to be executed with `-e, --eval "script"`. (on Windows only double quotes! bash or Powershell accept singles.)
```bash
node -e "console.log(123)"
```

### Auto restart application
As of nodejs V16, there is a built-in option to automatically restart the application when a file changes. This is useful for development purposes. To use this feature, the `--watch` flag needs to be passed:
```bash
node --watch app.js
```