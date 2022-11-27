# @reifiedbeans/prettier-config

[![npm version](https://img.shields.io/npm/v/@reifiedbeans/prettier-config/latest)](https://www.npmjs.com/package/@reifiedbeans/prettier-config)
![prettier version](https://img.shields.io/npm/dependency-version/@reifiedbeans/prettier-config/peer/prettier)
[![code style: prettier](https://img.shields.io/badge/code_style-prettier-ff69b4.svg)](https://github.com/prettier/prettier)
[![semantic-release: conventional commits](https://img.shields.io/badge/semantic_release-conventional_commits-e10079?logo=semantic-release)](https://github.com/semantic-release/semantic-release)
[![license: MIT](https://img.shields.io/npm/l/@reifiedbeans/prettier-config)](LICENSE)

A (somewhat) sensible [Prettier] config. This configuration sticks to the [Prettier defaults] for the most part, with a few changes that work better with [TypeScript] (in my opinion).

## Usage

First, install this package as a dev dependency.

```shell
npm install --save-dev @reifiedbeans/prettier-config
```

Then, add the following line to your `package.json`.

```json
{
  "prettier": "@reifiedbeans/prettier-config"
}
```

Finally, add some scripts to format your code, or, better yet, install the Prettier plugin for your editor, and set it up to auto-format on save.

## Rationale

This configuration makes a few changes to the Prettier default options. The following is my rationale for changing each of them.

### Print width

Default value: `80`
Configured value: `100`

I've found that, when writing TypeScript, it can be particularly easy to go over the 80 column mark. With type annotations, Prettier can print out some ugly looking code if it is forced to not go much over 80 columns. I think 100 columns gives enough breathing room to eliminate this issue in most circumstances without going overboard.

### Trailing commas

Default value: `"es5"`
Configured value: `"all"`

Trailing commas are really nice when you are making updates to a list.

> If you want to add a new property, you can add a new line without modifying the previously last line if that line already uses a trailing comma. This makes version-control diffs cleaner and editing code might be less troublesome.
>
> – [MDN Web Docs][mdn trailing commas]

By default, Prettier only permits trailing commas where they are valid in ES5. The docs mention that you can turn on trailing commas everywhere depending on your target.

> To run, JavaScript code formatted this way needs an engine that supports ES2017 (Node.js 8+ or a modern browser) or downlevel compilation. This also enables trailing commas in type parameters in TypeScript (supported since TypeScript 2.7 released in January 2018).
>
> – [Prettier documentation][prettier trailing commas]

If you're using TypeScript, this isn't really a concern, since the compiler can remove them if your target is set below ES2017.

## License

Licensed under the [MIT License](LICENSE).

[prettier]: https://prettier.io/
[prettier defaults]: https://prettier.io/docs/en/options.html
[typescript]: https://www.typescriptlang.org/
[mdn trailing commas]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Trailing_commas
[prettier trailing commas]: https://prettier.io/docs/en/options.html#trailing-commas
