# Parcel CSS entry issue

Possible fix: https://github.com/parcel-bundler/parcel/pull/9023

Repro: `pnpm install && pnpm dev`:

```
❯ pnpm dev

> bundle-name-collide@ dev /home/javascript/parcel/parcel-bug-css-name-collision
> (rm -rf .parcel-cache dist 2>&1 >/dev/null) && parcel build

🚨 Build failed.

@parcel/namer-default: Bundle group cannot have more than one entry bundle of the same type

  AssertionError [ERR_ASSERTION]: Bundle group cannot have more than one entry bundle of the same type
      at Object.name (/home/javascript/parcel/parcel-bug-css-name-collision/node_modules/.pnpm/@parcel+namer-default@2.9.3_@parcel+core@2.9.3/node_modules/@parcel/namer-default/lib/DefaultNamer.js:61:29)
      at BundlerRunner.nameBundle (/home/javascript/parcel/parcel-bug-css-name-collision/node_modules/.pnpm/@parcel+core@2.9.3/node_modules/@parcel/core/lib/requests/BundleGraphRequest.js:375:39)
      at /home/javascript/parcel/parcel-bug-css-name-collision/node_modules/.pnpm/@parcel+core@2.9.3/node_modules/@parcel/core/lib/requests/BundleGraphRequest.js:321:52
      at Array.map (<anonymous>)
      at BundlerRunner.bundle (/home/javascript/parcel/parcel-bug-css-name-collision/node_modules/.pnpm/@parcel+core@2.9.3/node_modules/@parcel/core/lib/requests/BundleGraphRequest.js:321:33)
      at process.processTicksAndRejections (node:internal/process/task_queues:95:5)
      at async Object.run (/home/javascript/parcel/parcel-bug-css-name-collision/node_modules/.pnpm/@parcel+core@2.9.3/node_modules/@parcel/core/lib/requests/BundleGraphRequest.js:126:17)
      at async RequestTracker.runRequest (/home/javascript/parcel/parcel-bug-css-name-collision/node_modules/.pnpm/@parcel+core@2.9.3/node_modules/@parcel/core/lib/RequestTracker.js:633:20)
      at async Object.run (/home/javascript/parcel/parcel-bug-css-name-collision/node_modules/.pnpm/@parcel+core@2.9.3/node_modules/@parcel/core/lib/requests/ParcelBuildRequest.js:51:7)
      at async RequestTracker.runRequest (/home/javascript/parcel/parcel-bug-css-name-collision/node_modules/.pnpm/@parcel+core@2.9.3/node_modules/@parcel/core/lib/RequestTracker.js:633:20)
```
