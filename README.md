1. `npm install`
2. `cp foo.sass ./node_modules/vite` - simulates sass file importable from some
   3rd party library
3. `npm run build`

At this point build crashes:

```
$ npm run build

> build
> vite build

vite v2.3.8 building for production...
transforming (1) index.htmlC:\dev\sass-bug\node_modules\sass\sass.dart.js:27420
      throw error;
      ^

Invalid argument(s): Uri c:%5Cdev%5Csass-bug%5Cnode_modules%5Cvite%5Cfoo.sass must have scheme 'file:'.
    at Object.wrapException (C:\dev\sass-bug\node_modules\sass\sass.dart.js:1231:17)
    at WindowsStyle.pathFromUri$1 (C:\dev\sass-bug\node_modules\sass\sass.dart.js:33230:17)
    at StaticClosure.fromUri (C:\dev\sass-bug\node_modules\sass\sass.dart.js:16163:37)
    at Object.NullableExtension_andThen0 (C:\dev\sass-bug\node_modules\sass\sass.dart.js:18504:40)
    at Object._wrapException (C:\dev\sass-bug\node_modules\sass\sass.dart.js:13047:14)
    at _render_closure1.call$2 (C:\dev\sass-bug\node_modules\sass\sass.dart.js:81775:21)
    at _RootZone.runBinary$3$3 (C:\dev\sass-bug\node_modules\sass\sass.dart.js:27547:18)
    at _FutureListener.handleError$1 (C:\dev\sass-bug\node_modules\sass\sass.dart.js:26096:19)
    at _Future__propagateToListeners_handleError.call$0 (C:\dev\sass-bug\node_modules\sass\sass.dart.js:26394:49)
    at Object._Future__propagateToListeners (C:\dev\sass-bug\node_modules\sass\sass.dart.js:4541:77) {
  dartException: <ref *1> ArgumentError {
    _hasValue: false,
    invalidValue: null,
    name: null,
    message: "Uri c:%5Cdev%5Csass-bug%5Cnode_modules%5Cvite%5Cfoo.sass must have scheme 'file:'.",
    '$thrownJsError': <ref *2> Invalid argument(s): Uri c:%5Cdev%5Csass-bug%5Cnode_modules%5Cvite%5Cfoo.sass must have scheme 'file:'.
        at Object.wrapException (C:\dev\sass-bug\node_modules\sass\sass.dart.js:1231:17)
        at WindowsStyle.pathFromUri$1 (C:\dev\sass-bug\node_modules\sass\sass.dart.js:33230:17)
        at StaticClosure.fromUri (C:\dev\sass-bug\node_modules\sass\sass.dart.js:16163:37)
        at Object.NullableExtension_andThen0 (C:\dev\sass-bug\node_modules\sass\sass.dart.js:18504:40)
        at Object._wrapException (C:\dev\sass-bug\node_modules\sass\sass.dart.js:13047:14)
        at _render_closure1.call$2 (C:\dev\sass-bug\node_modules\sass\sass.dart.js:81775:21)
        at _RootZone.runBinary$3$3 (C:\dev\sass-bug\node_modules\sass\sass.dart.js:27547:18)
        at _FutureListener.handleError$1 (C:\dev\sass-bug\node_modules\sass\sass.dart.js:26096:19)
        at _Future__propagateToListeners_handleError.call$0 (C:\dev\sass-bug\node_modules\sass\sass.dart.js:26394:49)
        at Object._Future__propagateToListeners (C:\dev\sass-bug\node_modules\sass\sass.dart.js:4541:77) {
      dartException: [Circular *1],
      '$cachedTrace': _StackTrace {
        _exception: [Circular *2],
        _trace: "Invalid argument(s): Uri c:%5Cdev%5Csass-bug%5Cnode_modules%5Cvite%5Cfoo.sass must have scheme 'file:'.\n" +
          '    at Object.wrapException (C:\\dev\\sass-bug\\node_modules\\sass\\sass.dart.js:1231:17)\n' +
          '    at WindowsStyle.pathFromUri$1 (C:\\dev\\sass-bug\\node_modules\\sass\\sass.dart.js:33230:17)\n' +
          '    at StaticClosure.fromUri (C:\\dev\\sass-bug\\node_modules\\sass\\sass.dart.js:16163:37)\n' +
          '    at Object.NullableExtension_andThen0 (C:\\dev\\sass-bug\\node_modules\\sass\\sass.dart.js:18504:40)\n' +
          '    at Object._wrapException (C:\\dev\\sass-bug\\node_modules\\sass\\sass.dart.js:13047:14)\n' +
          '    at _render_closure1.call$2 (C:\\dev\\sass-bug\\node_modules\\sass\\sass.dart.js:81775:21)\n' +
          '    at _RootZone.runBinary$3$3 (C:\\dev\\sass-bug\\node_modules\\sass\\sass.dart.js:27547:18)\n' +
          '    at _FutureListener.handleError$1 (C:\\dev\\sass-bug\\node_modules\\sass\\sass.dart.js:26096:19)\n' +
          '    at _Future__propagateToListeners_handleError.call$0 (C:\\dev\\sass-bug\\node_modules\\sass\\sass.dart.js:26394:49)\n' +
          '    at Object._Future__propagateToListeners (C:\\dev\\sass-bug\\node_modules\\sass\\sass.dart.js:4541:77)'
      }
    }
  }
}
```
