# Cml component support in Atom

Adds syntax highlighting and snippets to Cml component files in Atom.

Originally [converted](http://flight-manual.atom.io/hacking-atom/sections/converting-from-textmate/) from [cmljs/cml-syntax-highlight](https://github.com/cmljs/cml-syntax-highlight/tree/479672799b4162996e3c3c7e09583fb6d98e1e6c).

## Working with SCSS/Sass

Since cml-loader redirects `language=x` to loader `style!css!x` and sass-loader is using **SCSS** as default, you need to remap them in *webpack.config.js*:

```
cml: {
  loaders: {
    sass: 'style!css!sass?indentedSyntax',
    scss: 'style!css!sass'
  }
}
```

This is so that this package can support both old Sass and new SCSS. Refer to [hedefalk/atom-cml#5](https://github.com/hedefalk/atom-cml/issues/5) and [the official solution](https://github.com/cmljs-templates/webpack/blob/45c5ee5531a6f649c21aa2ec05472fb459247927/template/build/utils.js#L37-L38) for more info.
