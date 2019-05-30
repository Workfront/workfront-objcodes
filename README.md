# workfront-objcodes

[![NPM version][npm-version-image]][npm-url] [![NPM downloads][npm-downloads-image]][npm-url] [![Apache v2 License][license-image]][license-url] [![Build Status][travis-image]][travis-url]

Definitions for object codes to be used with Workfront API

## Usage

Package export 2 types of bundles:

 `dist/objcodes.js` - is ES6 module (ES6 import/export and ES5 code), which exports separate definitions for all object codes and also a single object named `ObjCodes` which contains values of all object codes.  
 This bundle is the default package entry point.
 
`dist/umb/objcodes.js` - is UMD bundle for ES5 environments.

We recommend to use `dist/objcodes.js` as it will allow tree-shaking feature of your favorite bundler to eliminate unused constants from the target bundle.  
The code inside `dist/objcodes.js` is in ES5, so you don't need transpilers to use it.


### Examples

```javascript
import {Baseline} from 'workfront-objcodes'

// output 'BLIN'
console.log(Baseline)
```

```javascript
import * as ObjCodes from 'workfront-objcodes'

// outputs 'BLIN'
console.log(ObjCodes.Baseline)
```

```typescript
// TypeScript type definitions are bundled
import {TObjCode, OpTask} from 'workfront-objcodes'

// TS2322: Type '"FOO"' is not assignable to type 'TObjCode' 
const myObjCode: TObjCode = 'FOO'

const myOtherObjCode = 'BAR' as const

function useObjCode(code: TObjCode) {
  // do something
}

useObjCode(OpTask)

// TS2345: Argument of type '"BAR"' is not assignable to parameter of type 'TObjCode'
useObjCode(myOtherObjCode)
```


## License

Copyright (c) 2019 Workfront

Licensed under the Apache License, Version 2.0.
See the top-level file `LICENSE` and
(http://www.apache.org/licenses/LICENSE-2.0).


[license-image]: http://img.shields.io/badge/license-APv2-blue.svg?style=flat
[license-url]: LICENSE

[npm-url]: https://www.npmjs.org/package/workfront-objcodes
[npm-version-image]: https://img.shields.io/npm/v/workfront-objcodes.svg?style=flat
[npm-downloads-image]: https://img.shields.io/npm/dm/workfront-objcodes.svg?style=flat

[travis-url]: https://travis-ci.org/Workfront/workfront-objcodes
[travis-image]: https://img.shields.io/travis/Workfront/workfront-objcodes.svg?style=flat
