author: Renuka Kelkar
summary: A public Google Codelab created from the terminal
id: public-google-codelab
categories: web
environments: Web
status: Published
feedback link: https://github.com/YOUR_GITHUB_USERNAME/public-google-codelab/issues

# Public Google Codelab from Terminal

## Overview
Duration: 2

This is a public Google Codelab-style tutorial created from Markdown using `claat`.

In this codelab, you will learn how to:

- Create a codelab source file
- Export it to static HTML
- Publish it publicly with GitHub Pages

## Step 1: Install claat
Duration: 3

Install the Google Codelabs command-line tool:

```bash
go install github.com/googlecodelabs/tools/claat@latest
export PATH="$PATH:$(go env GOPATH)/bin"
