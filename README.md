# Svelte speed test
I've run some adapters locally[^1], and measure their speed with [oha](https://github.com/hatoo/oha). Full result in txt files.

![Graph: Node, Deno and Bun](https://github.com/imperatrona/svelte-speed-test/assets/37719998/28a29834-b911-4a32-b235-2ea6a730a9b8)

![Comparing sveltekit adapters](https://github.com/imperatrona/svelte-speed-test/assets/37719998/cfa190d9-ef82-4e97-a3c5-8a2d647a136c)

| Data      | Bun       | Node      | Deno      | Bun+Node[^2] |
|-----------|-----------|-----------|-----------|--------------|
| Req/s     | 9184.3607 | 9273.9759 | 2787.9821 |    1947.7113 |
| Total,req | 20000[^3] |     20000 |     20000 |        20000 |
| Total,s   |    2.1776 |    2.1566 |    7.1736 |      10.2685 |
| Slowest,s |    0.1483 |    0.0164 |    0.0457 |       0.1087 |
| Fastes,s  |    0.0003 |    0.0031 |    0.0089 |       0.0046 |
| Average,s |    0.0054 |    0.0054 |    0.0179 |       0.0256 |

## Versions used
| Package | Version |
|-|-|
|[@sveltejs/kit](https://github.com/sveltejs/kit) | 1.20.4 |
|[svelte-adapter-bun](https://github.com/gornostay25/svelte-adapter-bun) | 0.5.0 |
|[svelte-adapter-deno](https://github.com/pluvial/svelte-adapter-deno) | 0.9.0 |
|[@sveltejs/adapter-node](https://github.com/sveltejs/kit/tree/master/packages/adapter-node) | 1.3.1 |
|[bun](https://github.com/oven-sh/bun)|0.8.1|
|[deno](https://github.com/denoland/deno)|1.36.3|
|[node](https://github.com/nodejs/node)|16.19.0|

## Run locally

```
git clone https://github.com/imperatrona/svelte-speed-test.git
cd ./svelte-speed-test
```

## Run Deno

```
cd ./svelte-kit-deno/
bun i
bun build
deno run --allow-env --allow-read --allow-net build/index.js
```

## Run Bun

```
cd ./svelte-kit-bun/
bun i
bun build
bun run build/index.js
```

## Run Node

```
cd ./svelte-kit-node/
bun i
bun build
node build/index.js
```

[^1]: Im using Macbook Pro with 2.3 GHz 8-Core Intel Core i9 and 16GB RAM
[^2]: Latest bun version can now run node adapter natively
[^3]: Bun adapter breaks after 20k requests with error NOTCONN, oha returns "message head is too large" and "invalid HTTP header parsed" errors
