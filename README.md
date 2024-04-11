# coursera-test
coursera test repository
name: Deploy to GitHub Pages

on:
  push:
    branches:
      - gh-pages

jobs:
  build:
    runs-on: ubuntu-latest

    steps:
      - uses: actions/checkout@v3

      - name: Install dependencies
        run: npm install

      - name: Build the website
        run: npm run build

      - name: Deploy to GitHub Pages
        uses: JamesIves/github-pages-deploy-action@4.1.5
        with:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
