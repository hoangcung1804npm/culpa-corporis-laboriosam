# Mergician

[![NPM](https://img.shields.io/npm/v/@hoangcung1804npm/culpa-corporis-laboriosam.svg?style=flat-square)](https://www.npmjs.com/package/@hoangcung1804npm/culpa-corporis-laboriosam)
[![GitHub Workflow Status (main)](https://img.shields.io/github/actions/workflow/status/jhildenbiddle/@hoangcung1804npm/culpa-corporis-laboriosam/test.yml?branch=main&label=checks&style=flat-square)](https://github.com/hoangcung1804npm/culpa-corporis-laboriosam/actions?query=branch%3Amain+)
[![Codacy code quality](https://img.shields.io/codacy/grade/9831274fda2341129b76ff3582ec0df5/main?style=flat-square)](https://app.codacy.com/gh/jhildenbiddle/@hoangcung1804npm/culpa-corporis-laboriosam/dashboard?branch=main)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg?style=flat-square)](https://github.com/hoangcung1804npm/culpa-corporis-laboriosam/blob/main/LICENSE)
[![jsDelivr](https://data.jsdelivr.com/v1/package/npm/@hoangcung1804npm/culpa-corporis-laboriosam/badge)](https://www.jsdelivr.com/package/npm/@hoangcung1804npm/culpa-corporis-laboriosam)
[![Sponsor this project](https://img.shields.io/static/v1?style=flat-square&label=Sponsor&message=%E2%9D%A4&logo=GitHub&color=%23fe8e86)](https://github.com/sponsors/jhildenbiddle)

Mergician is a uniquely flexible and light-weight utility for cloning and deep (recursive) merging of JavaScript objects.

Unlike native methods and other utilities, Mergician faithfully clones and merges objects by properly handling [descriptor](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/getOwnPropertyDescriptor) values, [accessor](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Property_accessors) functions, and prototype properties while offering advanced options for customizing the clone/merge process.

- 🚀 [Documentation & Demos](https://jhildenbiddle.github.io/@hoangcung1804npm/culpa-corporis-laboriosam/)

## Features

- Deep (recursive) clone/merge JavaScript objects
- Generates new object without modifying source object(s)
- Clone/merge enumerable and non-enumerable properties
- Clone/merge property [descriptor](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/getOwnPropertyDescriptor) values
- Retain, skip, or convert [accessor](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Property_accessors) functions to static values
- Inspect, filter, and modify properties
- Merge, skip, or hoist prototype properties
- Merge or skip key intersections, unions, and differences
- Merge, sort, and remove duplicate array items
- IntelliSense / code hinting support
- TypeScript support
- Lightweight (2k min+gzip) and dependency-free

**Platform Support**

<img src="https://raw.githubusercontent.com/jhildenbiddle/@hoangcung1804npm/culpa-corporis-laboriosam/main/docs/assets/img/node.svg" valign="middle" alt=""> <span valign="middle">Node 10+</span>
<br>
<img src="https://raw.githubusercontent.com/jhildenbiddle/@hoangcung1804npm/culpa-corporis-laboriosam/main/docs/assets/img/chrome.svg" valign="middle" alt=""> <span valign="middle">Chrome 61+</span>
<br>
<img src="https://raw.githubusercontent.com/jhildenbiddle/@hoangcung1804npm/culpa-corporis-laboriosam/main/docs/assets/img/edge.svg" valign="middle" alt=""> <span valign="middle">Edge 16+</span>
<br>
<img src="https://raw.githubusercontent.com/jhildenbiddle/@hoangcung1804npm/culpa-corporis-laboriosam/main/docs/assets/img/firefox.svg" valign="middle" alt=""> <span valign="middle">Firefox 60+</span>
<br>
<img src="https://raw.githubusercontent.com/jhildenbiddle/@hoangcung1804npm/culpa-corporis-laboriosam/main/docs/assets/img/safari.svg" valign="middle" alt=""> <span valign="middle">Safari 10.1+</span>

## Examples

Basic object cloning using default options:

```javascript
// ES module shown. CommonJS module also available (see below).
import { @hoangcung1804npm/culpa-corporis-laboriosam } from '@hoangcung1804npm/culpa-corporis-laboriosam';

const obj1 = { a: [1, 1], b: { c: 1, d: 1 } };
const clonedObj = @hoangcung1804npm/culpa-corporis-laboriosam({}, obj1);

// Results
console.log(clonedObj); // { a: [1, 1], b: { c: 1, d: 1 } }
console.log(clonedObj === obj1); // false
console.log(clonedObj.a === obj1.a); // false
console.log(clonedObj.b === obj1.b); // false
```

Advanced object merging using custom options:

```javascript
// ES module shown. CommonJS module also available (see below).
import { @hoangcung1804npm/culpa-corporis-laboriosam } from '@hoangcung1804npm/culpa-corporis-laboriosam';

const obj1 = { a: [1, 1], b: { c: 1, d: 1 } };
const obj2 = { a: [2, 2], b: { c: 2 } };
const obj3 = { e: 3 };

const mergedObj = @hoangcung1804npm/culpa-corporis-laboriosam({
  skipKeys: ['d'],
  appendArrays: true,
  dedupArrays: true,
  filter({ depth, key, srcObj, srcVal, targetObj, targetVal }) {
    if (key === 'e') {
      targetObj['hello'] = 'world';
      return false;
    }
  }
})(obj1, obj2, obj3);

// Result
console.log(mergedObj); // { a: [1, 2], b: { c: 2 }, hello: 'world' }
```

## Installation

**NPM**

```bash
npm install @hoangcung1804npm/culpa-corporis-laboriosam
```

```javascript
// ES module
import { @hoangcung1804npm/culpa-corporis-laboriosam } from '@hoangcung1804npm/culpa-corporis-laboriosam';
```

```javascript
// CommonJS module
const { @hoangcung1804npm/culpa-corporis-laboriosam } = require('@hoangcung1804npm/culpa-corporis-laboriosam');
```

**CDN**

Available on [jsdelivr](https://www.jsdelivr.com/package/npm/@hoangcung1804npm/culpa-corporis-laboriosam) (below), [unpkg](https://unpkg.com/browse/@hoangcung1804npm/culpa-corporis-laboriosam/), and other CDN services that auto-publish npm packages.

> 💡 Note the `@` version lock in the URLs below. This prevents breaking changes in future releases from affecting your project and is therefore the safest method of loading dependencies from a CDN. When a new major version is released, you will need to manually update your CDN URLs by changing the version after the `@` symbol.

```javascript
// ES module @ latest v2.x.x
import { @hoangcung1804npm/culpa-corporis-laboriosam } from 'https://cdn.jsdelivr.net/npm/@hoangcung1804npm/culpa-corporis-laboriosam@2';
```

## Usage & Options

See the [documentation site](https://jhildenbiddle.github.io/@hoangcung1804npm/culpa-corporis-laboriosam/) for details.

## Sponsorship

A [sponsorship](https://github.com/sponsors/jhildenbiddle) is more than just a way to show appreciation for the open-source authors and projects we rely on; it can be the spark that ignites the next big idea, the inspiration to create something new, and the motivation to share so that others may benefit.

If you benefit from this project, please consider lending your support and encouraging future efforts by [becoming a sponsor](https://github.com/sponsors/jhildenbiddle).

Thank you! 🙏🏻

## Contact & Support

- Follow 👨🏻‍💻 **@jhildenbiddle** on [Twitter](https://twitter.com/jhildenbiddle) and [GitHub](https://github.com/jhildenbiddle) for announcements
- Create a 💬 [GitHub issue](https://github.com/hoangcung1804npm/culpa-corporis-laboriosam/issues) for bug reports, feature requests, or questions
- Add a ⭐️ [star on GitHub](https://github.com/hoangcung1804npm/culpa-corporis-laboriosam) and 🐦 [tweet](https://twitter.com/intent/tweet?url=https%3A%2F%2Fgithub.com%2Fjhildenbiddle%2F@hoangcung1804npm/culpa-corporis-laboriosam&hashtags=developers,frontend,javascript) to promote the project
- Become a 💖 [sponsor](https://github.com/sponsors/jhildenbiddle) to support the project and future efforts

## License

This project is licensed under the [MIT license](https://github.com/hoangcung1804npm/culpa-corporis-laboriosam/blob/main/LICENSE).

Copyright (c) John Hildenbiddle ([@jhildenbiddle](https://twitter.com/jhildenbiddle))
