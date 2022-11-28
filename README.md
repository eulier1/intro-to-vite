# Intro To Vite

Vite a the french word for fast and this is a next gen of build tools for front-end.
It comes with a 
- Dev server and also 
- Bundles you code for production.

The problem that Vite is trying to solve really is the **feedback loop speed during development**.

If you use Vue-CLI specially in a large project, you’re used to waiting for half a minute or up to a minute for you dev server to spin up, when the project gets larger HMR get slower aswell, just adding a single file can take few seconds for things to update on the screen.

Now a lot of these problems are fundamentally cause by the re-up **by the need of bundling**.
Why do we have bundlers?.

Because in the old days, **there were no** native mechanism for **authoring** js in a **modularize** way, that’s why we are familiar with such concepts. 
So in the early days we invented things system like **AMD** or **Common.js** and we wrote such code in those formats and then we pass it to lab tools like **webpack**, **parcel** or **browserify**, to bundle such code so that finally they become a single file that can be run in the browser.

So luckily today most modern browser support **ESM**, this means that on development there is a large chunk of work that we no longer need to do it, because the browser can now handle it natively.

So the **promise of Vite** is that we’re going to **author** our **code** as native **ESM**, so the browser will take these ES modules, parse it and look for the **import statement** and then send http request for each module to the dev server.

And the dev server they just going to serve those file **as is** with very lightweight processing, so a lot of the work are done by the browser, natively, so there is little preparation when we start the server

Another aspect of these, if you have **large dependencies**, vite will smartly **pre-bundle** them using ES build to reduce the number of request that the browser needs to make to the dev server, now this bundling process is done with **ES Build** is an excellent tool written by **Evan Wallace** the CTO of **Figma** and it is written in **go** which is a compile to native language so it’s order of magnitude faster that equivalent tools written in JS.

So with these factors combine, vite provides an extremely fast and lean DX.

Vite is framework agnostic.
