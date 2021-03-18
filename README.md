# outdated

[![NPM version](https://img.shields.io/npm/v/@ruyadorno/outdated)](https://www.npmjs.com/package/@ruyadorno/outdated)
[![License](https://img.shields.io/github/license/ruyadorno/outdated)](https://github.com/ruyadorno/outdated/blob/master/LICENSE)

Shortcut to interactively update your deps using npm + ipt

> An [iPipeTo](https://github.com/ruyadorno/ipt) workflow

<br />
<br />

<p align="center">
<img alt="demo animation" width="600" src="https://ruyadorno.github.io/svg-demos/outdated/outdated.svg" />
</a>
</p>

<br />

## Install

Get it with **npm**:

```sh
npm install -g @ruyadorno/outdated ipt
```

### Run

In any npm project you want to update a dependency, run:

```
outdated
```

**OR**

bypass **npm install** and run it at once using **npx**:

```sh
npx @ruyadorno/outdated
```

## Features

- Interactively list top-level dependencies that needs updating
- `outdated latest` will build an interactive list using the **Latest**
option from `npm outdated`

### Note on Wanted vs Warning versions:

**npm outdated** will provide two targets to update to: Wanted/Warning:
  - A **Wanted** version is a newer version that satisfies the current
  semver-range defined in your `package.json`
  - A **Latest** version is whatever is the latest version of that dependency
  published to the configured registry for that project.

## Requirements

- [npm cli](https://github.com/npm/cli)
- [ipt](https://www.npmjs.com/package/ipt)

## Help

```
outdated

Options:
        outdated                Open interactive menu updating deps to a "Wanted" version
        outdated latest Open interactive menu updating deps to a "Latest" version
        --help                  Show this help menu
        --version               Prints version number
```

### Equivalent bash alias

Although less powerful, this bash alias achieves roughly the same base usage of
pipping the result of `npm outdated` into `ipt` for a interactive experience.

```sh
alias outdated="npm install $(npm outdated --parseable | cut -d ':' -f 2 | ipt)"
```

## License

[MIT](LICENSE) © 2021 [Ruy Adorno](https://ruyadorno.com)
