
# Routes

## In web client programming, the current route means:

👉 The URL path (and sometimes query string or hash) that the web application is currently showing to the user.


## In a traditional website:

* Each URL (e.g., /about, /contact) corresponds to a separate HTML page served by the server.

* The “route” is essentially the URL that determines which page is loaded.


## In a Single Page Application (SPA, like React apps):

* The app loads once (usually at /index.html).

* The current route is managed on the client side by a router library (e.g., React Router, Vue Router).

* The route decides which component(s) should be rendered for the given URL, without reloading the whole page.


## Example with React Router:

```
<Routes>
   <Route path="/" element={<Home />} />
   <Route path="/about" element={<About />} />
</Routes>
```

If the browser’s URL is https://example.com/about, then:

* The current route is /about.

* React Router renders the <About /> component.