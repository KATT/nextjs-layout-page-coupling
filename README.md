Demos recompilation of of `page.js` being slow due to `layout.js` being complex

In the layout here, we have a loop that blocks the event loop for 10s:

https://github.com/KATT/nextjs-layout-page-coupling/blob/5eaecca1a0b96bfb7e59b9cc57c36c6a4728f690/app/layout.js#L6-L9

The page itself is dead simple, but changing it gets punished by the layout being complex.

https://github.com/KATT/nextjs-layout-page-coupling/blob/5eaecca1a0b96bfb7e59b9cc57c36c6a4728f690/app/page.js#L1-L3

- Open pnpm dev
- Go to localhost:3000
- First load is slow and that's ok
- Change `page.js` -> wait
