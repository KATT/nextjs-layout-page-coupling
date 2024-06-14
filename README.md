Demos recompilation of of `page.js` being slow due to `layout.js` being complex

In the layout here, we have a loop that blocks the event loop for 10s:

https://github.com/KATT/nextjs-layout-page-coupling/blob/b953729d0039c6133fe8de7f78bec69b173c360a/app/layout.js#L6-L9

- Open pnpm dev
- Go to localhost:3000
- First load is slow and that's ok
- Change `page.js` -> wait
