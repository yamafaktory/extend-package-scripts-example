# extend-package-scripts-example

An example of how to extend your package.json scripts by passing extra files or flags as arguments.

## Install

```bash
git clone git@github.com:yamafaktory/extend-package-scripts-example.git

npm i
```

## Why

1. [npm](https://www.npmjs.com/) is an amazing package manager and an *efficient build tool / task runner* too.

2. You do not need to install / wrap your mind around / configure another bloated tool to get the stuff done.

3. You like Unix and so does npm.

## How

Please first take a look at the [package.json file](https://github.com/yamafaktory/extend-package-scripts-example/blob/master/package.json).

```json
"config": {
  "file": "example.es6"
},
"scripts": {
  "compile": "babel --presets es2015 $npm_package_config_file",
  "compile:file": "npm run-script compile -- -o file.js",
  "compile:watch": "npm run-script compile -- -w -o file.js"
}
```

You will notice that:

- You can create your own variables in the *config* section.

- You can reuse these variables in the *script* section (e.g. `$npm_package_config_whatever`).

- You can create extended tasks on purpose by appending `--` plus new arguments to one given initial task.

## Is that new?

[Absolutely not.](http://blog.npmjs.org/post/98131109725/npm200)

Please read the [documentation](https://docs.npmjs.com/cli/run-script).
