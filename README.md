# @edemaine/meteor-tracker

[Meteor Tracker](https://docs.meteor.com/api/tracker.html) is a dependency
tracking system from [Meteor](https://www.meteor.com/).

This NPM package `@edemaine/meteor-tracker` offers a drop-in replacement for
the `meteor/tracker` module available in [Meteor](https://www.meteor.com/)
(with the [`tracker` package](https://atmospherejs.com/meteor/tracker)),
so that it can be used in other JavaScript projects,
in particular for testing NPM packages that are intended for Meteor
but testing from outside Meteor (e.g. [via Jest](#usage-jest)).

The code consists of a one-line change to
[Meteor's source code](https://github.com/meteor/meteor/blob/devel/packages/tracker/tracker.js),
to make the Node module exports match the Meteor exports
(`Tracker` and `Deps`).

The intent is to track the version numbers of Meteor Tracker.
If the latter changes, please open an issue to update this package.

## Usage: JavaScript

To install:

```sh
npm install meteor-tracker
```

In your JavaScript code, you can use:

```js
import {Tracker} from '@edemaine/meteor-tracker';
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
  },
```
