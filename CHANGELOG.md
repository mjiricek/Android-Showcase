**0.5.0**
* `Either` - class has been moved to the functional library. [ ![Download](https://api.bintray.com/packages/ahead/Architecture/functional/images/download.svg) ](https://bintray.com/ahead/Architecture/functional/_latestVersion)  

**0.4.0**
* `ViewModelBaseActivity` - now contains a default constructor (0 argument constructor).

**0.3.2**
* `ViewModelBaseActivity` - moved the VM injection before onInitializeView

**0.3.1**
* `Either.onLeft` - Replaced parameter in lambda expression. From `fnL: (L) -> Nothing` to `fnL: (Either.Left<L>) -> Nothing`.

**0.3.0**
* Removed `getViewModel()` getter
* `viewModel` is now directly accessible in fragments
* `foldAsync, mapAsync, flatMapAsync, withRightAsync` are now deprecated.
* `ViewModelBaseFragment, SharedViewModelBaseFragment, ViewModelBaseActivity` now contain a constructor that takes a @LayoutRes Int.
* Added `Either.onLeft`. This extension function returns the right value if `Either.isRight == true` or aborts current function otherwise.
* Removed specific failures: `Failure.ServerError`, `Failure.EmptyBodyError`, `Failure.HttpError`

**0.2.0**
* `Either.foldAsync` extension is added.

**0.1.1**
* `Either.flatMapAsync` returns a new `Either.Left` instance with the same content if `Either.isLeft == true`.
* `Either.withRightAsync` returns the same `Either.Left` instance if `Either.isLeft == true`.

**0.1.0**
* `SingleLiveEvent` is now deprecated. Use `LiveEvent` instead.
