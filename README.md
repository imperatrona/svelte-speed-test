# Svelte speed test
I've run some adapters locally, and measure their speed with [oha](https://github.com/hatoo/oha). Full result in txt files.

![Graph: Node, Deno and Bun](https://user-images.githubusercontent.com/37719998/189484075-aa195fb5-dd04-4e9f-817b-f290622d9a32.svg)
|Data|Node|Deno|Bun|
|-|-|-|-|
|Req/s|1682.1434|1263.8154|6243.3276|
|Total,s|0.1189|0.1583|0.0320|
|Slowest,s|0.0402|0.1069|0.0120|
|Fastes,s|0.0117|0.0153|0.0037|
|Average,s|0.0275|0.0368|0.0061|


## Versions used
| Package | Version |
|-|-|
|[@sveltejs/kit](https://github.com/sveltejs/kit) | 1.0.0-next.304 |
|[@sveltejs/adapter-node](https://github.com/sveltejs/kit/tree/master/packages/adapter-node) | 1.0.0-next.73|
|[svelte-adapter-deno](https://github.com/pluvial/svelte-adapter-deno) | 0.6.2|
|[svelte-adapter-bun](https://github.com/gornostay25/svelte-adapter-bun) | 0.3.0|



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
