# skipUntil

####signature: `skipUntil(the: Observable): Observable`

## Skip emitted values from source until provided observable emits.

<div class="ua-ad"><a href="https://ultimatecourses.com/courses/rxjs"><img src="https://ultimatecourses.com/assets/img/banners/rxjs-banner-desktop.svg" style="width:100%;max-width:100%"></a></div>

### Examples

##### Example 1: Skip until observable emits

(
[StackBlitz](https://stackblitz.com/edit/typescript-gs4mps?file=index.ts&devtoolsheight=100)
| [jsBin](http://jsbin.com/tapizososu/1/edit?js,console) |
[jsFiddle](https://jsfiddle.net/btroncone/xLu8nf77/) )

```js
// RxJS v6+
import { interval, timer } from 'rxjs';
import { skipUntil } from 'rxjs/operators';

//emit every 1s
const source = interval(1000);
//skip emitted values from source until inner observable emits (6s)
const example = source.pipe(skipUntil(timer(6000)));
//output: 5...6...7...8........
const subscribe = example.subscribe(val => console.log(val));
```

### Additional Resources

- [skipUntil](https://rxjs.dev/api/operators/skipUntil)
  :newspaper: - Official docs

---

> :file_folder: Source Code:
> [https://github.com/ReactiveX/rxjs/blob/master/src/internal/operators/skipUntil.ts](https://github.com/ReactiveX/rxjs/blob/master/src/internal/operators/skipUntil.ts)
