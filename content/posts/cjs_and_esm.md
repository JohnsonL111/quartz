---
title: "Common JS vs. ESM: what the heck javascript"
tags: ["Educational"]
date: 2025/06/22
---

It was a rainy hump day and I'm writing unit tests at my coop. Well, it's a greenfield project so I had the splendid choice of choosing the unit testing library. For backend, I made the choice of mocha + chai + sinon for mocking + nyc for code coverage. Although I could've went with Jest which is like a 4 in 1, which I already had experience in I wanted to try something new and additionally the company already used the mocha+chai combo in other projects.

Anyways, for the frontend the obvious choice was jest... right? Well, turns out configuring jest for the modern frontend that uses a JS UI library like React, Vue, or Angular is nothing short of painful.

Firstly, Jest ships as CommonJS (CJS) by default, whereas react ships as ECMAScript Modules (ESM). This mismatch means that to use Jest in react projects, you often need to configure Jest to handle ESM, or transpile your project back to CJS for compatibility.

Secondly, if you are using typescript (which I was) you have to configure `ts-jest` too or configure babel for transpilation.

This is just the tip of the iceberg of config hell.

What the heck javascript.

## An ode to Vite

Thankfully, vitest exists. Since I was using vite as the build tool (which basically everyone uses after CRA was deprecated unless you're a bun user which in that case you aren't even using the node ecosystem) vitest is basically just a zero-config drop-in.

This made me realize how much I appreciate the work Vite abstracts from the developer. It uses ESBuild which just makes any translation layer (like `jsx -> js` and `ts -> js`, or combined... `.tsx` -> `.ts`) work seamlessly. And everything being in a single `vite.config.ts` is crazy.

## How did we get here?

So how did we get to this mess of an ecosystem where we have two import/export styles. I mean, in other languages there's typically just one dominant way to import/export code.

Well, it's basically because people want javascript everywhere.

![js_quote](js.png)

Way back then, CJS was adopted by node projects so it was dominant in the backend API space with Express and in CLI tooling like npm. CJS is `syncronous` and blocking which is fine since these use cases were typically load once run forever (until the server crashes) in the case of APIs and for CLI tooling it was no concern.

Notice how frontend was never in the picture for node projects?

When the ECMAscript standard released ESM modules it was targetted for browsers. I mean, JS was originally for browsers so it was time to standardize things. It was `asyncronous` which was perfect for browsers since it wasn't blocking the UI. ESM modules were also flexible and you could _choose exactly what to import_ which opened the door for tree shaking.

This meant you could have for example a `math` ESM module, and on build time Vite will use ESBuild to "tree shake" or remove unused functions. This was huge for reducing bundle sizes and its only possible in ESM modules.

```js
// math.mjs
export function add(a, b) {
  return a + b
}

export function multiply(a, b) {
  return a * b
}

export function subtract(a, b) {
  return a - b
}
```

The `multiply` and `subtract` functions will be removed from the final bundle since they aren't used.

```js
// main.mjs
import { add } from "./math.mjs"

console.log(add(2, 3))
```

Anyways, back to the main topic.

Even before ESM modules were released, the web dev world was booming with SPAs via React, Vue, and angular. These were node libraries that were tailored to make more modular frontend applications with reusable components.

Wait a minute? Node projects (CJS) in a frontend (ESM) environment?

That's where the confusion happens.

React, for example, was written in CJS but the browser with the latest ECMAscript6 update only supported ESM. So now you need a translation layer that converts cjs into something the browser could understand.

## The Result

Although if you use Vite it abstracts all the translation away from you it's still kind of insightful to learn about the behind the scenes. It also explains a lot of the reason why some people detest working on JS projects sometimes (besides the fact its not typed - just use typescript folks).

Nowadays, most modern node packages ship as ESM and there's a continuous effort to provide ESM variants of legacy packages but its still an ongoing effort to interop the two.

## Deno

A random aside, but I'm curious to see where the future of web dev goes with the rise of alternative runtimes like Deno (who was made by the person who made Node). Personally, I see myself staying in the node ecosystem just from familiarity, but I heard Deno only supports ESM and if I have to deal with interopping ESM and CJS through config hell I may just switch 🗿.
