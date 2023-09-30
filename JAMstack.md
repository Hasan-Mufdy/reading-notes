# JAMstack

## What is the JAMstack?

To start, JAMstack is a software architecture and philosophy that adheres to the following components: Javascript, APIs, and Markup.

If this sounds familiar, it's because it is! That React app that you compile down with Webpack and ultimately serve from S3? Yup, that’s a JAMstack app. That simple HTML file that has no JavaScript and literally doesn’t do anything dynamic? Yup, that’s also a JAMstack app.

#### That’s not to be confused with serverless

If you’re coming more from the cloud side of things (think AWS, GCP, Azure), you might be inclined to think of serverless and JAMstack as the same thing. Granted they have similarities in the philosophy of how resources are managed, such as hosting a site on S3. But a JAMstack app is not always going to be a serverless app.

Consider an app hosted in static storage on the cloud provider of your choice. Yes, you might be serving the app in a serverless way, but you might be dealing with an API that utilizes Wordpress or Rails, both of which are certainly not serverless.

Combining these philosophies can go a long way, but they shouldn’t be confused as the same.

## What makes up the JAMstack?

Back to the JAMstack: it's typically comprised of 3 components: Javascript, APIs, and Markup. Its history stems from growing the term "static site" into something more meaningful (and marketable). So while ultimately a static site is the end result, it's blown up to include first class tooling for every step of the way.
While there aren't any specific set of tools that you need to use, or any tools at all beyond simple HTML, there are great examples of what can make up each part of the stack.

### Javascript

The component that’s probably done the most work to popularize the JAMstack is Javascript. Our favorite browser language allows us to provide all of the dynamic and interactive bits that we might not have if we’re serving plain HTML without it.

This is where a lot of times you’ll see UI frameworks like React, Vue, and newcomers like Svelte come into play.

They make building apps simpler and more organized by providing component APIs and tooling that compile down to a simple HTML file (or a bunch of them).
Those HTML files include a group of assets like images, CSS, and the actual JS that ultimately get served to a browser via your favorite CDN (content delivery network).

### APIs

Utilizing the strengths of APIs is core to how you make a JAMstack app dynamic. Whether it’s authentication or search, your application will use Javascript to make an HTTP request to another provider which will ultimately enhance the experience in one form or another.

### Markup

This is the critical piece. Whether it’s your hand written HTML or the code that compiles down to the HTML, it's the first part you’re serving to the client.
