<p align="center">
  <img src="./compress.jpg" alt="aws-actions" height="196px">
</p>
<h1 style="font-size: 56px; margin: 0; padding: 0;" align="center">
  compress
</h1>
<p align="center">
  <img src="https://badgen.net/badge/TypeScript/strict%20%F0%9F%92%AA/blue" alt="Strict TypeScript">
  <img src="https://img.shields.io/badge/commitizen-friendly-brightgreen.svg" alt="Commitizen friendly">
  <img src="https://snyk.io/test/github/clowdhaus/compress/master/badge.svg" alt="Known Vulnerabilities">
</p>

GitHub action to compress executables using `upx`.

## Usage

`upx` man page for reference:

```
Usage: upx [-123456789dlthVL] [-qvfk] [-o file] file..

Commands:
  -1     compress faster                   -9    compress better
  -d     decompress                        -l    list compressed file
  -t     test compressed file              -V    display version number
  -h     give more help                    -L    display software license
Options:
  -q     be quiet                          -v    be verbose
  -oFILE write output to 'FILE'
  -f     force compression of suspicious files
  -k     keep backup files
file..   executables to (de)compress
```

```yml
- uses: clowdhaus/compress@v0.1
  with:
    # Commands [-123456789dlthVL]
    commands: ''

    # Options [-qvfk] [-o file]
    options: ''

    # Executable file to compress
    # required: true
    file: ''
```

## Scenarios

### Compress executable using default settings

```yml
- uses: clowdhaus/compress@v0.1
  with:
    file: myExecutable.exe
```

### Compress executable with highest level of compression with verbose output

```yml
- uses: clowdhaus/compress@v0.1
  with:
    commands: -9
    options: -v
    file: myExecutable.exe
```

### Compress executable leaving original file untouched and generating a new, compressed file

```yml
- uses: clowdhaus/compress@v0.1
  with:
    options: -o newExecutable.exe
    file: some/path/myExecutable.exe
```

## Getting Started

The following instructions will help you get setup for development and testing purposes.

### Prerequisites

#### [yarn](https://github.com/yarnpkg/yarn)

`yarn` is used to handle dependencies and executing scripts on the codebase.

See [here](https://yarnpkg.com/en/docs/install#debian-stable) for instructions on installing yarn on your local machine.

Once you have installed `yarn`, you can install the project dependencies by running the following command from within the project root directory:

```bash
  $ yarn
```

## Contributing

Please read [CODE_OF_CONDUCT.md](CODE_OF_CONDUCT.md) for details on our code of conduct and the process for submitting pull requests.

## Changelog

Please see the [CHANGELOG.md](../CHANGELOG.md) for details on individual releases.
