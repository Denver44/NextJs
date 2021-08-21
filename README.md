**Code-based Routing**

    1. BoilerPlate setup in code required
    2. Straightforward but includes new components + concepts.
    3. File + Folder setup doesn't matter at all.
    4. Navigation works with Link component and imperatively.

**File-based Routing**

    1. No extra boiler plate required
    2. Intuitive system
    3. File + folder structure (in pages/folder) influences routes
    4. Navigation works with Link component and imperatively

**Create React component files and let NextJs infer the router from the folder structure**

## The special /pages folder

```
/pages
|- index.js------->localhost:3000 ---------------------------- SPECIAL PATH
|- about.js------->localhost:3000/about----------------------- STATIC PATH
| -/product
| - index.js------->localhost:3000/product
| - [id].js-------->localhost:3000/product/anything ---- DYNAMIC PATH
```

### Extracting Dynamic Path Segment Data (Dynamic Routes)

    1. We have to use a Hook called useRouter from 'next/router and when working with classes then withRouter.
    1. useRouter() return a object.
    2. we can use various methods like pathname,query (return a object it will give the concrete value).

### we can have dynamic routes & path

    1. We can have a dynamic folder also.
    2. Nextjs will get all path after blog here.
    3. [...name].js it will catch all route path : example localhost:3000/blog/2012/12/5 (here 2012/12/5 will be extracted.)
    4. now we will get array of the (name) eg ['2012','12','5']

### Why to use Link?

    1. Using a anchor tag it actually makes a http request and page reload because of that redux loose it state and start re-fetching so use Link component.
    2. In place of anchor tag use Link.
    3. Link take href props which take a string of route.
    4. To Navigate dynamic page also we used Link

### Special 404 Page iin NextJs

    1. create 404.js file to show your Custom Error page
    2. else nextjs will show its Default Error page.

### IMPORTANT

    - File Name are Case Sensitive.
    - create a next.config.js file to allow that page only which has pageExtension mentioned in that file.
    - Because of next.config.js we can create our unit tests "file.specs.js" and Next.js will not create/open a new route at http://localhost:3000/file.spec
