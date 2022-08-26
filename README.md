# SSCCE for elm-codegen local install file bug.

## Expected behavior

`elm-codegen install codegen/helpers/LocalFile.elm` creates helper. Then it runs with `elm-codegen run`.

## Actual behavior

`elm-codegen install codegen/helpers/LocalFile.elm` creates helper. Then it _errors_ with `elm-codegen run`.

## To reproduce inside SSCCE project

    elm-codegen run

## Error

    Error: ENOENT: no such file or directory, open 'generated/codegen/helpers/LocalFile.elm'

### Full stacktrace

```
node:fs:585
  handleErrorFromBinding(ctx);
  ^

Error: ENOENT: no such file or directory, open 'generated/codegen/helpers/LocalFile.elm'
    at Object.openSync (node:fs:585:3)
    at Object.writeFileSync (node:fs:2155:35)
    at _loop_1 (/Users/absynce/.npm/_npx/be14e040090c2b5c/node_modules/elm-codegen/dist/run.js:521:16)
    at copyHelpers (/Users/absynce/.npm/_npx/be14e040090c2b5c/node_modules/elm-codegen/dist/run.js:540:9)
    at Command.<anonymous> (/Users/absynce/.npm/_npx/be14e040090c2b5c/node_modules/elm-codegen/dist/run.js:706:13)
    at step (/Users/absynce/.npm/_npx/be14e040090c2b5c/node_modules/elm-codegen/dist/run.js:71:23)
    at Object.next (/Users/absynce/.npm/_npx/be14e040090c2b5c/node_modules/elm-codegen/dist/run.js:52:53)
    at /Users/absynce/.npm/_npx/be14e040090c2b5c/node_modules/elm-codegen/dist/run.js:46:71
    at new Promise (<anonymous>)
    at __awaiter (/Users/absynce/.npm/_npx/be14e040090c2b5c/node_modules/elm-codegen/dist/run.js:42:12) {
  errno: -2,
  syscall: 'open',
  code: 'ENOENT',
  path: 'generated/codegen/helpers/LocalFile.elm'
}
```

## System info:

    node -v
    v16.14.0

    elm-codegen -V
    0.1.0
