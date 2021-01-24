# Vanilla JavaScript Swipe

> :medal: All credits go to Ana Tudor for her post on [CSS Tricks](https://css-tricks.com/): [Simple Swipe with Vanilla JavaScript](https://css-tricks.com/simple-swipe-with-vanilla-javascript/)

## Changes from the original

1. Installed `node-sass`: `npm i -D node-sass`, and added a `build:css` script in `package.json` to regenerate `style.css` from `style.scss`.
2. Installed Prettier & ESLint (w/ Airbnb style guide):

    * `npm i -D prettier eslint`
    * `npx eslint --init` (let it install additional deps: `eslint-config-airbnb-base` and `eslint-plugin-import`)
3. Ran Prettier on all files: `npx prettier --write .`
4. Added a `fmt-lint` script to first format with Prettier, then lint (it's usually the other way round, but who cares).