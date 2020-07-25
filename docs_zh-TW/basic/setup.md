---
id: setup
title: 設定
---

## 預先要求

1. 已經對 [React](https://reactjs.org) 有一定程度的理解
2. 熟悉 [TypeScript Types](https://www.typescriptlang.org/docs/handbook/basic-types.html) ([2ality's guide](http://2ality.com/2018/04/type-notation-typescript.html) 是相當有幫助的。如果你是一個完全 TypeScript 的初學者，可以先看 [chibicode’s tutorial](https://ts.chibicode.com/todo/).)
3. 已經閱讀過 [the TypeScript section in the official React docs](https://reactjs.org/docs/static-type-checking.html#typescript).
4. 已經閱讀過 [the React section of the new TypeScript playground](http://www.typescriptlang.org/play/index.html?jsx=2&esModuleInterop=true&e=181#example/typescript-with-react) (可選的: 也一步步執行這裡的超過40個的範例: [the playground's](http://www.typescriptlang.org/play/index.html) 範例單元)

在這個指引中，將會總是假設你目前使用的是最新版本的 TypeScript 。所以舊版本的部份將會被註記在，可展開的 `<details>` 標記中。

## React + TypeScript Starter Kits

1. [Create React App v2.1+ with TypeScript](https://facebook.github.io/create-react-app/docs/adding-typescript): `npx create-react-app my-app --template typescript`

- 我們之前是建議  `create-react-app-typescript` 但它現在已經被 [deprecated(棄用)] (https://www.reddit.com/r/reactjs/comments/a5919a/createreactapptypescript_has_been_archived_rip/)。[觀看移轉的指示說明](https://vincenttunru.com/migrate-create-react-app-typescript-to-create-react-app/)

1. [Basarat's guide](https://github.com/basarat/typescript-react/tree/master/01%20bootstrap) 這一篇是針對 **手動設定** 有關於 React + TypeScript + Webpack + Babel

- 特別要注意的是，確認你的確在專案裡有 `@types/react` 與 `@types/react-dom` 已經安裝好了 ([閱讀更多有關於 DefinitelyTyped 專案，如果你還不熟悉的話](https://definitelytyped.org/))
- 也有更多 React + TypeScript boilerplates(腳手架)，請看 [我們下面的資源列表](https://github.com/typescript-cheatsheets/react-typescript-cheatsheet#recommended-react--typescript-codebases-to-learn-from).

## Import(導入) React

```tsx
import * as React from "react";
import * as ReactDOM from "react-dom";
```

在 [TypeScript 2.7+](https://www.typescriptlang.org/docs/handbook/release-notes/typescript-2-7.html) 中，你可以在執行 TypeScript 時加上`--allowSyntheticDefaultImports` (或是加上 `"allowSyntheticDefaultImports": true` 到 tsconfig) 來像一般的jsx一樣的 import(導入) 方式:

```tsx
import React from "react";
import ReactDOM from "react-dom";
```

<details>

<summary>解說</summary>

為什麼使用 `allowSyntheticDefaultImports` 而不用 `esModuleInterop`? [Daniel Rosenwasser](https://twitter.com/drosenwasser/status/1003097042653073408) 曾說過這對於 webpack/parcel 是較好的方式。要看更多的討論請看 <https://github.com/wmonk/create-react-app-typescript/issues/214>

你應該也要看一下 [新的 TypeScript 官方文件，有關每個編譯器的旗標之間的說明](https://www.typescriptlang.org/v2/en/tsconfig#allowSyntheticDefaultImports)!

</details>
