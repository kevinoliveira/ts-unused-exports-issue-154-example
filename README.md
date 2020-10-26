# ts-unused-exports issue-154

`src/main.ts` imports and uses two functions, `sayHelloWorld` and `sayHelloWorldInJapanese`, but the latter is wrongly reported as unused, see output below.

```
> npm run start

> issue-154@1.0.0 start /home/USER/r/154-issue
> ts-node --compiler ttypescript --project ./tsconfig.json src/main.ts

Hello World
こんにちは世界
```

```
> npm run not-used

> issue-154@1.0.0 not-used /home/USER/r/154-issue
> ts-unused-exports ./tsconfig.json

1 module with unused exports
/home/USER/r/154-issue/src/very/long/path/to/file/helpers.ts: sayHelloWorldInJapanese
```