# github-label

[![NPM version](http://img.shields.io/npm/v/github-label.svg)](https://www.npmjs.org/package/github-label)
[![license](http://img.shields.io/badge/license-MIT-brightgreen.svg)](https://github.com/codenameyau/github-label/blob/master/LICENSE)

Node command-line tool used to create or remove GitHub labels.
Predefined labels are available in the [presets folder](https://github.com/codenameyau/github-label/tree/master/presets).
You can also create and use your own labels with JSON.

## Installation and Setup
```
npm install -g github-label
```

### Authentication with GitHub Access Token
Use this method if don't want to type your username and password.

Create a [Personal access token](https://github.com/settings/tokens) on GitHub
with the `repo` and `public_repo` permissions enabled. Then add the following
environment variable in your `.bashrc` (Linux) or `.bash_profile` (Mac).

```bash
export GITHUB_LABEL_TOKEN='REPLACE THIS WITH YOUR TOKEN'
```

## Usage Examples

```
  Usage: github-label [options]

  Options:

    -h, --help            output usage information
    -V, --version         output the version number
    -p, --preset [value]  Specify a label preset.
    -l, --list [value]    List the default preset.
    -j, --json [value]    Specify your own JSON label preset.
    -s, --skip            Skip existing labels instead of updating them.
    -r, --remove          Remove a GitHub label preset.
    -R, --remove-all      Removes all labels.
```

--

### Terminal
```bash
# Output the labels for the repository.
github-label 'codenameyau/github-label'

# List the available label presets.
github-label -l

# List the labels for a given preset.
github-label -l priority

# Create labels with one of the available presets.
github-label 'codenameyau/github-label' -p priority

# Create labels by specifying your own JSON.
github-label 'codenameyau/github-label' -j 'path-to/preset.json'

# Delete all labels from a given preset or json file.
github-label 'codenameyau/github-label' -p priority -r
github-label 'codenameyau/github-label' -j 'path-to/preset.json' -r

# Remove all labels.
github-label 'codenameyau/github-label' -R
```
