#1 Server-Side Rendering

See https://docsify.now.sh

Repo in https://github.com/docsifyjs/docsify-ssr-demo

#2 Why SSR?
- Better SEO
- Feeling cool

#2 Quick start

Install `now` and `docsify-cli` in your project.

```bash
npm i now docsify-cli -D
```

Edit `package.json`. If the documentation in `./docs` subdirectory.

```json
{
  "name": "my-project",
  "scripts": {
    "start": "docsify start . -c ssr.config.js",
    "deploy": "now -p"
  },
  "files": [
    "docs"
  ],
  "docsify": {
    "config": {
      "basePath": "https://docsify.js.org/",
      "loadSidebar": true,
      "loadNavbar": true,
      "coverpage": true,
      "name": "docsify"
    }
  }
}
```

!> The `basePath` just like webpack `publicPath`. We can use local or remote files.

We can preview in the local to see if it works.

```bash
npm start

#1 open http://localhost:4000
```

Publish it!

```bash
now -p
```

Now, You have a support for SSR the docs site.

#2 Custom template

You can provide a template for entire page's HTML. such as

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>docsify</title>
  <meta name="viewport" content="width=device-width, initial-scale=1.0, minimum-scale=1.0">
  <link rel="stylesheet" href="//cdn.jsdelivr.net/npm/docsify/themes/vue.css" title="vue">
</head>
<body>
  <!--inject-app-->
  <!--inject-config-->
  <script src="//cdn.jsdelivr.net/npm/docsify/lib/docsify.js"></script>
  <script src="//cdn.jsdelivr.net/npm/docsify/lib/plugins/search.js"></script>
  <script src="//cdn.jsdelivr.net/npm/prismjs/components/prism-bash.min.js"></script>
  <script src="//cdn.jsdelivr.net/npm/prismjs/components/prism-markdown.min.js"></script>
  <script src="//cdn.jsdelivr.net/npm/prismjs/components/prism-nginx.min.js"></script>
</body>
</html>
```

The template should contain these comments for rendered app content.
 - `<!--inject-app-->`
 - `<!--inject-config-->`

#2 Configuration

You can configure it in a special config file, or `package.json`.

```js
module.exports = {
  template: './ssr.html',
  maxAge: 60 * 60 * 1000, // lru-cache config
  config: {
   // docsify config
  }
}
```

#2 Deploy for your VPS

You can run `docsify start` directly on your Node server, or write your own server app with `docsify-server-renderer`.

```js
var Renderer = require('docsify-server-renderer')
var readFileSync = require('fs').readFileSync

// init
var renderer = new Renderer({
  template: readFileSync('./docs/index.template.html', 'utf-8'),
  config: {
    name: 'docsify',
    repo: 'docsifyjs/docsify'
  }
})

renderer.renderToString(url)
  .then(html => {})
  .catch(err => {})
```
