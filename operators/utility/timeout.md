# timeout

#### signature: `timeout(due: number, scheduler: Scheduler): Observable`

## Error if no value is emitted before specified duration

<div class="ua-ad"><a href="https://ultimatecourses.com/courses/rxjs"><img src="https://ultimatecourses.com/assets/img/banners/rxjs-banner-desktop.svg" style="width:100%;max-width:100%"></a></div>

### Examples

##### Example 1: Timeout after 2.5 seconds

(
[StackBlitz](https://stackblitz.com/edit/typescript-eegqyz?file=index.ts&devtoolsheight=100)
| [jsBin](http://jsbin.com/gonakiniho/edit?js,console) |
[jsFiddle](https://jsfiddle.net/btroncone/nr4e1ofy/1/) )

```js
// RxJS v6+
import { of } from 'rxjs';
import { concatMap, timeout, catchError, delay } from 'rxjs/operators';

// simulate request
function makeRequest(timeToDelay) {
  return of('Request Complete!').pipe(delay(timeToDelay));
}

of(4000, 3000, 2000)
  .pipe(
    concatMap(duration =>
      makeRequest(duration).pipe(
        timeout(2500),
        catchError(error => of(`Request timed out after: ${duration}`))
      )
    )
  )
  /*
   *  "Request timed out after: 4000"
   *  "Request timed out after: 3000"
   *  "Request Complete!"
   */
  .subscribe(val => console.log(val));
```

### Additional Resources

- [timeout](https://rxjs.dev/api/operators/timeout)
  :newspaper: - Official Docs

---

> :file_folder: Source Code:
> [https://github.com/ReactiveX/rxjs/blob/master/src/internal/operators/timeout.ts](https://github.com/ReactiveX/rxjs/blob/master/src/internal/operators/timeout.ts)
