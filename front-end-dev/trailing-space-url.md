# What's the Meaning of the Trailing Space at the End of An Url
I have always been wondering the difference between these two:

```
http://example.com/about/
http://example.com/about
```

As a matter of fact, the trailing space makes a little difference on how it directs you to the 
correct page. I found a good explanation in the `flask` documentation, which says:

> Though they look rather similar, they differ in their use of the trailing slash in the URL definition. In the first case, the canonical URL for the projects endpoint has a trailing slash. In that sense, it is similar to a **folder** on a filesystem. Accessing it without a trailing slash will cause Flask to redirect to the canonical URL with the trailing slash.

> In the second case, however, the URL is defined without a trailing slash, rather like the pathname of a file on UNIX-like systems. Accessing the URL with a trailing slash will produce a 404 “Not Found” error.

