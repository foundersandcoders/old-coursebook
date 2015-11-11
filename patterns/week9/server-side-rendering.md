## What is Isomorphic JavaScript?

TL;DR: JavaScript rendered on the server AND the client.
In a nutshell, you are rendering your application markup on the server & piping it down as the complete html to the browser.
(Sidenote: Isomorphism is also a mathematical term that means something different, but whatever. This is about JS)

### Why is it useful?

Isomorphic JavaScript is useful for a number of reasons, lets run through the major ones.

- 1. FasterPerceived Load Times + Better Global UX

With the proliferation of more and more of the web being driven by JavaScript, The speed of the browser DOM is becoming increasingly noticeable.
Lots of sites being driven by popular JavaScript frameworks like Ember, Backbone, or Angular can take a while to render into the DOM. This forces the user to wait for the app to bootstrap itself before they can start viewing & ‘using’ the app.
Making users wait for an app to bootstrap is a sub-par user experience. It is easily avoidable by implementing server-side rendering.
When you render your applications markup on the server, the page loads immediately to the user and they can start doing whatever they what without any wait.

- 2. Search Engine Indexability

One of the primary reasons for doing ‘isomorphic’ javascript is for better visible for search engines.
If your application is public facing (ie not behind a login), having you application data indexed is critical for growing organic traffic to your application.
While google notes that they do javascript rendering as of May 23rd 2014, they state “It’s always a good idea to have your site degrade gracefully.” IE rendering on the server, so if the client does not have javascript enabled, the person can still see the site.
A live example of Google’s Javascript rendering/indexing can be seen on Bustle.com, which is actually missing a chunk of the page in google’s cache
In my opinion, I think it’s best to not leave the indexation of your application to chance. Setup server side rendering and you can be sure that the markup is going to be crawled correctly.

- 3. Free Progressive Enhancements

Let’s say you have a form in your react application that binds some events to it’s submission process. What happens if the person has javascript disabled in their browser? You app won’t work.
While this is a pretty extreme edge case, it can happen. This person will see a blank screen and have a sad face.
If you rendered that markup on the server, the visitor would still see the styled markup with the form intact. That form should have the normal action parameter to POST it’s results to the same endpoint your react application is pointing to.
A great live example of the ‘free progressive enhancements’ can be seen on the react router mega demo. If you turn off your browser’s javascript, the directory still functions normally.
You can see the code for the react router mega demo here. It’s a fantastic example of isomorphic serverside rendering by Ryan Florence.

- 4. Easier Code Maintenance

When implementing an isomorphic solution, We use the same code base*
This makes code debt and code maintenance less of a headache.
*While the code base on client/server are the same, the implementation is slightly different on server vs client. Let’s
