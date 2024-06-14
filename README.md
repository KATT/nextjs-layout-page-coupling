Demos recompilation of of `page.js` being slow due to `layout.js` being complex

In the layout here, we have a loop that blocks the event loop for 10s:

https://github.com/KATT/nextjs-layout-page-coupling/blob/5eaecca1a0b96bfb7e59b9cc57c36c6a4728f690/app/layout.js#L6-L9

The page itself is dead simple, but changing it gets punished by the layout being complex.

https://github.com/KATT/nextjs-layout-page-coupling/blob/5eaecca1a0b96bfb7e59b9cc57c36c6a4728f690/app/page.js#L1-L3

This isn't a big problem itself - who writes silly code like that, right? - Well, the issue is exasperated by the dev server being very slow on any barrel imports so any complex layout with many imports will have a pretty bad experience when developing.

---

```shell
git clone git@github.com:KATT/nextjs-layout-page-coupling.git
cd nextjs-layout-page-coupling
pnpm i
pnpm dev
```

- Run `pnpm dev`
- Go to localhost:3000
- First load is slow and that's ok
- Change `page.js` -> wait
