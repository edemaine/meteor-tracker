# @edemaine/meteor-tracker

[Meteor Tracker](https://docs.meteor.com/api/tracker.html) is a dependency
tracking system from [Meteor](https://www.meteor.com/).  Together with
[Meteor ReactiveVar](https://docs.meteor.com/api/reactive-var.html),
it makes it easy to rerun code when dependencies change.

This NPM package `@edemaine/meteor-tracker` offers a drop-in replacement for
the `meteor/tracker` and `meteor/reactive-var` modules available in
Meteor with the [`tracker`](https://atmospherejs.com/meteor/tracker) and
[`reactive-var`](https://atmospherejs.com/meteor/reactive-var) packages,
so that it can be used in other JavaScript projects,
in particular for testing NPM packages that are intended for Meteor
but testing from outside Meteor (e.g. [via Jest](#usage-jest)).

The code consists of a few one-line changes to Meteor's source code
(see `CHANGE FOR NPM` in the code),
to make the Node module imports and exports match those in Meteor.

For a more complete set of Meteor ports, check out
[Blast](https://github.com/harryadel/blastjs) on
[NPM](https://www.npmjs.com/search?q=%40blastjs).

## Versions

The intent is to track the latest version of Meteor Tracker.
If the latter changes, please open an issue to update this package.

NPM version | Meteor versions
------------|----------------
1.0.x | [tracker 1.2.0](https://github.com/meteor/meteor/tree/4a76fe3fe6bbb99ce2850690864c5bbad97ec163/packages/tracker)
1.1.x | [tracker 1.2.0](https://github.com/meteor/meteor/tree/4a76fe3fe6bbb99ce2850690864c5bbad97ec163/packages/tracker), [reactive-var 1.0.11](https://github.com/meteor/meteor/tree/f39812bd4bc024734dd48b77c97930f9ba07f3c9/packages/reactive-var)

## Usage: JavaScript

To install:

```sh
npm install meteor-tracker
```

In your JavaScript code, you can use:

```js
import {Tracker} from '@edemaine/meteor-tracker';
import {ReactiveVar} from '@edemaine/meteor-tracker';
```

## Usage: Jest

To install:

```sh
npm install --save-dev meteor-tracker
```

To use this module for testing in Jest as a substitute for `meteor/tracker`,
add the following to your Jest configuration:

```js
  moduleNameMapper: {
    '^meteor/tracker$': '@edemaine/meteor-tracker',
    '^meteor/reactive-var$': '@edemaine/meteor-tracker',
  },
```
