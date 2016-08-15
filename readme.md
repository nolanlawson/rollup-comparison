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

**Update!** After uglify + gzip, i.e. `uglifyjs -mc | gzip -c | wc -c`:

```
845	dist/bundle-browserify.js
681	dist/bundle-browserify-es5-only.js
548	dist/bundle-webpack.js
382	dist/bundle-webpack-es5-only.js
250	dist/bundle-rollup.js
```

**Update:** Added closure, results:

> note that closure must be in local folder, I added a link to the command like this:   
> ln -s ~/.bin/compiler.jar  
> note also that --compilation_level must be a value of WHITESPACE_ONLY, SIMPLE, or ADVANCED  
> (I used SIMPLE) see https://developers.google.com/closure/compiler/docs/compilation_levels

ADVANCED

```
1053 bundle-rollup.js.closure.js
1533 bundle-rollup.js.uglify.js
1652 bundle-rollup.js

3203 bundle-webpack.js.closure.js
3700 bundle-webpack.js.uglify.js

4022 bundle-browserify.js.closure.js
4527 bundle-browserify.js.uglify.js
6274 bundle-browserify.js

7442 bundle-webpack.js

```

SIMPLE  
(it seems closure perform better on webpack & browserify)

```
1533 bundle-rollup.js.uglify.js
1537 bundle-rollup.js.closure.js
1652 bundle-rollup.js

3375 bundle-webpack.js.closure.js
4199 bundle-browserify.js.closure.js
5288 bundle-webpack.js.uglify.js
5709 bundle-browserify.js.uglify.js
6274 bundle-browserify.js
7442 bundle-webpack.js
```
