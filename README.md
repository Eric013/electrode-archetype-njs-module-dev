# Builder Archetype: Hapi Plugin (Development)

A Walmart Labs flavored Hapi Plugin archetype for [builder][].

## Installation

If you want to use `builder` as a CLI tool (recommended), follow the instructions at
[formidablelabs/builder to modify your `PATH`](https://github.com/formidablelabs/builder#local-install)

Within your project, run:

```sh
$ npm install --save-dev builder @walmart/electrode-archetype-hapi-plugin-dev
```

Add a `.builderrc` that contains the following:

```yaml
---
archetypes:
  - "@walmart/electrode-archetype-hapi-plugin-dev"
```

## Project Structure

This archetype assumes an architecture as follows:

```
.builderrc
.npmrc
.gitignore
package.json

lib/
  index.js

test/
  spec/**
    *.spec.js
```

## Tasks

```
$ builder help 

Usage:

  builder <action> <task(s)>

Actions:

  help, run, concurrent, envs

Flags: General

  --builderrc: Path to builder config file (default: `.builderrc`)

Tasks:

  check
    [@walmart/electrode-archetype-hapi-plugin-dev] builder run lint && builder run test-cov

  check-ci
    [@walmart/electrode-archetype-hapi-plugin-dev] builder run lint && builder run test-ci

  lint
    [@walmart/electrode-archetype-hapi-plugin-dev] builder concurrent lint-lib lint-test

  lint-lib
    [@walmart/electrode-archetype-hapi-plugin-dev] eslint -c node_modules/@walmart/electrode-archetype-hapi-plugin-dev/config/eslint/.eslintrc-node lib --color

  lint-test
    [@walmart/electrode-archetype-hapi-plugin-dev] eslint -c node_modules/@walmart/electrode-archetype-hapi-plugin-dev/config/eslint/.eslintrc-test test --color

  test
    [@walmart/electrode-archetype-hapi-plugin-dev] mocha -c --opts node_modules/@walmart/electrode-archetype-hapi-plugin-dev/config/test/mocha.opts test/spec

  test-ci
    [@walmart/electrode-archetype-hapi-plugin-dev] builder run test-cov

  test-cov
    [@walmart/electrode-archetype-hapi-plugin-dev] istanbul cover _mocha -- -c --opts node_modules/@walmart/electrode-archetype-hapi-plugin-dev/config/test/mocha.opts test/spec
```

[builder]: https://github.com/FormidableLabs/builder

