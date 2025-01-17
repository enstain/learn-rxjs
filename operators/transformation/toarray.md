# toArray

#### signature: `toArray(): OperatorFunction`

## Collects all source emissions and emits them as an array when the source completes.

<div class="ua-ad"><a href="https://ultimatecourses.com/courses/rxjs"><img src="https://ultimatecourses.com/assets/img/banners/rxjs-banner-desktop.svg" style="width:100%;max-width:100%"></a></div>

### Examples

##### Example 1: get values emitted by interval as an array when interval completes

(
[StackBlitz](https://stackblitz.com/edit/rxjs-toarray?file=index.ts&devtoolsheight=100)
)

```js
// RxJS v6+
import { interval } from 'rxjs';
import { toArray, take } from 'rxjs/operators';

interval(100)
  .pipe(
    take(10),
    toArray()
  )
  .subscribe(console.log);

// output: [0, 1, 2, 3, 4, 5, 6, 7, 8, 9]
```

### Related Recipes

- [Breakout Game](../../recipes/breakout-game.md)
- [Lockscreen](../../recipes/lockscreen.md)

### Additional Resources

- [toArray](https://rxjs.dev/api/operators/toArray)
  :newspaper: - Official docs

---

> :file_folder: Source Code:
> [https://github.com/ReactiveX/rxjs/blob/master/src/internal/operators/toArray.ts](https://github.com/ReactiveX/rxjs/blob/master/src/internal/operators/toArray.ts)
