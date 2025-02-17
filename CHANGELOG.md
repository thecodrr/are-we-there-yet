# Changelog

## [4.0.1](https://github.com/npm/are-we-there-yet/compare/v4.0.0...v4.0.1) (2023-07-17)

### Bug Fixes

* [`aee9063`](https://github.com/npm/are-we-there-yet/commit/aee90632efbeb9d2d0efc98e4a8346906bc0fe3f) [#178](https://github.com/npm/are-we-there-yet/pull/178) modernize class inheritance (#178) (@jimmywarting)

## [4.0.0](https://github.com/npm/are-we-there-yet/compare/v3.0.1...v4.0.0) (2022-10-10)

### ⚠️ BREAKING CHANGES

* `are-we-there-yet` is now compatible with the following semver range for node: `^14.17.0 || ^16.13.0 || >=18.0.0`

### Features

* [`529459c`](https://github.com/npm/are-we-there-yet/commit/529459c24875a8210c5fb472dcb6199cfea61acd) [#157](https://github.com/npm/are-we-there-yet/pull/157) postinstall for dependabot template-oss PR (@lukekarrys)

### Dependencies

* [`7af13fa`](https://github.com/npm/are-we-there-yet/commit/7af13fa1388e09abbbf4ce7e2ac6bb7a5fb81bc5) [#146](https://github.com/npm/are-we-there-yet/pull/146) bump readable-stream from 3.6.0 to 4.1.0

## [3.0.1](https://github.com/npm/are-we-there-yet/compare/v3.0.0...v3.0.1) (2022-07-21)


### Bug Fixes

* replace deprecated String.prototype.substr() ([#140](https://github.com/npm/are-we-there-yet/issues/140)) ([6145a9e](https://github.com/npm/are-we-there-yet/commit/6145a9ef6908c0feb107ac41f704e0aabe2718d0))

## [3.0.0](https://www.github.com/npm/are-we-there-yet/compare/v2.0.0...v3.0.0) (2022-02-09)


### ⚠ BREAKING CHANGES

* This drops support for node10 and non-LTS versions of node 12 and node 14

### Bug Fixes

* @npmcli/template-oss@2.7.1 ([f742777](https://www.github.com/npm/are-we-there-yet/commit/f7427775fcf59185b99693d2e5480e1185de8589))


### Documentation

* rename CHANGE.md to CHANGELOG.md ([2667644](https://www.github.com/npm/are-we-there-yet/commit/2667644d37bf9d1d9c25cdf3a133d607f151b8c2))

## 1.1.5 2018-05-24

* [#92](https://github.com/iarna/are-we-there-yet/pull/92) Fix bug where
  `finish` would throw errors when including `TrackerStream` objects in
  `TrackerGroup` collections.  (@brianloveswords)

## 1.1.4 2017-04-21

* Fix typo in package.json

## 1.1.3 2017-04-21

* Improve documentation and limit files included in the distribution.

## 1.1.2 2016-03-15

* Add tracker group cycle detection and tests for it

## 1.1.1 2016-01-29

* Fix a typo in stream completion tracker

## 1.1.0 2016-01-29

* Rewrote completion percent computation to be low impact– no more walking a
  tree of completion groups every time we need this info.  Previously, with
  medium sized tree of completion groups, even a relatively modest number of
  calls to the top level `completed()` method would result in absurd numbers
  of calls overall as it walked down the tree. We now, instead, keep track as
  we bubble up changes, so the computation is limited to when data changes and
  to the depth of that one branch, instead of _every_ node. (Plus, we were already
  incurring _this_ cost, since we already bubbled out changes.)
* Moved different tracker types out to their own files.
* Made tests test for TOO MANY events too.
* Standarized the source code formatting
