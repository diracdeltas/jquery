# What is this?

This is a fork of jQuery 1.11.3 that only breaks when built with
a particular version of the minifier (uglify-js@2.4.23, possibly earlier
versions though I haven't checked). It was used to make the PoC described in
[this blog post](https://zyan.scripts.mit.edu/blog/backdooring-js/).

`./html` includes HTML files that behave differently in "interesting" ways depending on whether the included jquery script is minified.

## Building a non-broken build

```
$ npm install
$ grunt
```

## Building a broken build

```
$ npm install
```

Open `node_modules/grunt-contrib-uglify/package.json` and set `"uglify-js": "2.4.23"` in the "dependencies" field. Then to force `grunt-contrib-uglify` to install this particular version of `uglify-js`:

```
$ cd node_modules/grunt-contrib-uglify
$ rm -r node_modules
$ npm install
$ cd ../..
$ grunt
```
