# Babel Base Project

Use this project as a base for your ECMAScript6 webmodule projects
that use Babel.

## Setup instructions

1. Clone/copy the contents of this repo to a new folder.
2. Fill in your webmodule information in `package.json`, replacing
   `YOUR-WEBMODULE-NAME` with the webmodule name and so on. Make
   sure you remove the `"private": true` line to allow `npm publish`
   to work.
3. Add your code to the root directory. `.js` files inside the `build`
   directory are generated by Babel.
4. Use `make build` to build the `.js` files inside the `build` dir.
   They're also generated automatically before publishing. (Check the
   `prepublish` script in `package.json`)
5. Replace this readme with the readme of your webmodule project.
6. Push to github, then `npm publish`.

## Important Remarks

* Do not to commit the generated `.js` files inside `build` to Git.
* The `babel-runtime` dependency is used by babel to polyfill ES6
  features and to load helper functions. Given how fast babel is
  being updated, we've decided to specify only the major version
  to avoid having webmodules with different runtime versions on
  the same dependency tree. (Otherwise we'd need to constantly
  update all ES6 webmodules to follow babel's releases) If that
  proves to be a problem, (e.g. breakage) we'll change this strategy.
* A locally installed copy of babel is used to build, so you don't
  need a global `babel(1)` tool installed on your system.

## Todo

- Add test code / make rules.

## License

MIT