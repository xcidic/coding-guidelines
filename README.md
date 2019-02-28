This Repo is development version of coding guidelines for each Xcidic members to follows. Build version published in [Branch:gh-pages](https://github.com/xcidic/coding-guidelines/tree/gh-pages)

## Needs
1. [Hugo](https://gohugo.io) version 0.25.1. See Installation for [specific version](https://gohugo.io/getting-started/installing/).
2. [Quickstart](https://gohugo.io/overview/quickstart/)
3. [docdock theme v1.0](https://themes.gohugo.io/docdock/)

## Setup
1. Clone this project. `git clone --recursive git@github.com:xcidic/coding-guidelines.git`

2. Enter Project folder `cd coding-guidelines`

3. This project included docdock theme already. If you delete it accidentally. You can simply clone the docdock theme

```bash
git clone https://github.com/vjeantet/hugo-theme-docdock.git --branch v1.0.0 themes/docdock
```

## Run
   ```bash
    # Run dev
    hugo server

    # Run build
    hugo 

   ```

## Build destination folder
- `public/`

## Release to github pages
1. run `hugo` to build pages in [master](https://github.com/xcidic/coding-guidelines/tree/master) branch
2. checkout to [gh-pages](https://github.com/xcidic/coding-guidelines/tree/gh-pages) branch
   ```bash
    # first clone
    git fetch && git checkout gh-pages
    
    # or
    # you have gh-pages branch in local
    git checkout gh-pages
   ```
3. copy everything inside public to root folder
   ```bash
    cp -a public/ ./
   ```
4. commit and push to [gh-pages](https://github.com/xcidic/coding-guidelines/tree/gh-pages) branch
