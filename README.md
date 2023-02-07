![Screenshot 2023-02-07 105851](https://user-images.githubusercontent.com/93249038/217157355-8673b262-ae44-41c3-be6d-6af4312a191d.png)


## Installation and Usage

# ES6 via npm
npm install rxjs

It's recommended to pull in the Observable creation methods you need directly from 'rxjs' as shown below with range. If you're using RxJS version 7.2 or above, you can pull in any operator you need from the same spot, 'rxjs'.

import { range, filter, map } from 'rxjs';

range(1, 200)
  .pipe(
    filter(x => x % 2 === 1),
    map(x => x + x)
  )
  .subscribe(x => console.log(x));
If you're using RxJS version below 7.2, you can pull in any operator you need from one spot, under 'rxjs/operators'.

import { range } from 'rxjs';
import { filter, map } from 'rxjs/operators';

range(1, 200)
  .pipe(
    filter(x => x % 2 === 1),
    map(x => x + x)
  )
  .subscribe(x => console.log(x));

# CDN
For CDN, you can use unpkg:

https://unpkg.com/rxjs@^7/dist/bundles/rxjs.umd.min.js

The global namespace for rxjs is rxjs:

const { range } = rxjs;
const { filter, map } = rxjs.operators;

range(1, 200)
  .pipe(
    filter(x => x % 2 === 1),
    map(x => x + x)
  )
  .subscribe(x => console.log(x));
  
# Goals

Smaller overall bundles sizes
Provide better performance than preceding versions of RxJS

To model/follow the Observable Spec Proposal to the observable

Provide more modular file structure in a variety of formats

Provide more debuggable call stacks than preceding versions of RxJS

# Building/Testing
npm run compile build everything

npm test run tests

npm run dtslint run dtslint tests
