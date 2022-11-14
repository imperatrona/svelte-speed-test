# Svelte speed test
I've run some adapters locally, and measure their speed with [oha](https://github.com/hatoo/oha). Full result in txt files.

![Graph: Node, Deno and Bun](https://user-images.githubusercontent.com/37719998/201751378-824aa5c9-9aa7-454b-b09b-b31917c6987c.svg)

|Data|Node|Deno|Bun|
|-|-|-|-|
|Req/s|1682.1434|3248.5757|6243.3276|
|Total,s|0.1189|30.7827|0.0320|
|Slowest,s|0.0402|0.0827|0.0120|
|Fastes,s|0.0117|0.0090|0.0037|
|Average,s|0.0275|0.0154|0.0061|


## Versions used
| Package | Version | [@sveltejs/kit](https://github.com/sveltejs/kit) version |
|-|-|-|
|[@sveltejs/adapter-node](https://github.com/sveltejs/kit/tree/master/packages/adapter-node) | 1.0.0-next.73 | 1.0.0-next.304 |
|[svelte-adapter-deno](https://github.com/pluvial/svelte-adapter-deno) | 0.8.1 | 1.0.0-next.406 |
|[svelte-adapter-bun](https://github.com/gornostay25/svelte-adapter-bun) | 0.3.0 | 1.0.0-next.304 |



## Run locally

```
git clone https://github.com/jonaaronru/svelte-speed-test.git
cd ./svelte-speed-test
```

## Run Deno

```
cd ./svelte-kit-deno/
yarn
yarn build
deno run --allow-env --allow-read --allow-net build/index.js
```

## Run Bun

```
cd ./svelte-kit-bun/
yarn
yarn build
cd ./build
bun run start
```

## Run Node

```
cd ./svelte-kit-node/
yarn yarn build
node build/index.js
```
