# Svelte speed test
I've run some adapters locally[^1], and measure their speed with [oha](https://github.com/hatoo/oha). Full result in txt files.

![Graph: Node, Deno and Bun](https://user-images.githubusercontent.com/37719998/201763013-bd33a09a-508c-4429-b305-26c2d82f9fe7.svg)



|Data|Node|Deno|Bun|
|-|-|-|-|
|Req/s|9023.8510|3248.5757|6143.0011|
|Total,req|100k|100k|10k[^2]|
|Total,s|11.0817|30.7827|1.6279|
|Slowest,s|0.0233|0.0827|0.0255|
|Fastes,s|0.0029|0.0090|0.0006|
|Average,s|0.0055|0.0154|0.0081|

## Versions used
| Package | Version |
|-|-|
|[@sveltejs/kit](https://github.com/sveltejs/kit) | 1.0.0-next.406 |
|[@sveltejs/adapter-node](https://github.com/sveltejs/kit/tree/master/packages/adapter-node) | 1.0.0-next.100 |
|[svelte-adapter-deno](https://github.com/pluvial/svelte-adapter-deno) | 0.8.1 |
|[svelte-adapter-bun](https://github.com/gornostay25/svelte-adapter-bun) | 0.3.1 |



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

[^1]: Im using Macbook Pro with 2.3 GHz 8-Core Intel Core i9 and 16GB RAM
[^2]: Bun adapter breaks after 10k requests with error NOTCONN, oha returns "message head is too large" and "invalid HTTP header parsed" errors
