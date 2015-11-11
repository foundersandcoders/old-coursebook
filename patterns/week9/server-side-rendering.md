## What is an Isomorphic web app?

An isomorphic web app is one which uses both server-side and client-side rendering.

### Server-side rendering

Server side, the react app or component is rendered into html (without interactivity eg click handlers), which gets served to the client. This means that when the page loads client side, some static content is visible very quickly.

### Client-side rendering

When the page loads in the browser, as well as the static content, there will be a script tag linking to your bundle file (created in webpack or browserify or similar).
```
<script src="bundle.js" ></script>
```
The static content is visible almost immediately, whilst the bundle.js file is read by the browser. The bundle.js file inserts the interactive react app/component into the page, replacing the static content.

(Sidenote: Isomorphism is also a mathematical term that means something different, but whatever. This is about JS)

## Why is it useful?

**FasterPerceived Load Times + Better Global UX**

Since a static version (rendered server side) is visible while the javascript loads. 

**Search Engine Indexability**

Since a static version (rendered server side) is visible by search engine bots.

**Free Progressive Enhancements**

Since not everyone will have javascript enabled, they will at least be able to see the static version (rendered server side).

**Easier Code Maintenance**

All your code is in one place.
