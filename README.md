# npm-overrides-bug
Repository to highlight bug for `npm ci` when used on versions above `8.5.5`


Node Version: 16.14.2 or newer
NPM Version: 8.6.0 or newer

This repo was set up with `npm@8.7.0` and running `npm install`


### Problem
If this repo is cloned and `npm ci` is run the following error is displayed:

<img width="783" alt="Screenshot 2022-05-19 at 15 47 58" src="https://user-images.githubusercontent.com/3385622/169308932-50b6963c-310d-4fa3-8f19-90af957d95ef.png">

Listing the conflicts that npm detects from `package-lock.json`.

If `npm i` is used at this time or `npm i --package-lock-only` the following security vulnerabilities which were overriden in the `package.json` become restored:

<img width="441" alt="Screenshot 2022-05-19 at 15 50 50" src="https://user-images.githubusercontent.com/3385622/169309595-5d3d75ae-26d2-4823-b870-9460e77b0e3c.png">

This behaviour is consistent on versions 8.6.0, 8.7.0, 8.8.0, 8.9.0, 8.10.0 with these dependencies.




### Workaround
If downgraded to `npm@8.5.5` the `npm ci` command runs without error.
