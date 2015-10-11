compare rollup to browserify/webpack
----

basic comparison of rollup to browserify/webpack, for the case of a module
that imports 20 small functions from 20 other modules.

usage:

```
npm run browserify
npm run browserify-es5-only
npm run webpack
npm run webpack-es5-only
npm run rollup
```

result (bytes):

```
6274	dist/bundle-browserify.js
4248	dist/bundle-browserify-es5-only.js
7442    dist/bundle-webpack.js
5275	dist/bundle-webpack-es5-only.js
1652    dist/bundle-rollup.js
```
