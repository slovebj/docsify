#1 List of Plugins

#2 Full text search

By default, the hyperlink on the current page is recognized and the content is saved in `localStorage`. You can also specify the path to the files.

```html
<script>
  window.$docsify = {
    search: 'auto', // default

    search : [
      '/',            // => /README.md
      '/guide',       // => /guide.md
      '/get-started', // => /get-started.md
      '/zh-cn/',      // => /zh-cn/README.md
    ],

    // complete configuration parameters
    search: {
      maxAge: 86400000, // Expiration time, the default one day
      paths: [], // or 'auto'
      placeholder: 'Type to search',

      // Localization
      placeholder: {
        '/zh-cn/': '搜索',
        '/': 'Type to search'
      },

      noData: 'No Results!',

      // Localization
      noData: {
        '/zh-cn/': '找不到结果',
        '/': 'No Results'
      },

      // Headline depth, 1 - 6
      depth: 2,

      hideOtherSidebarContent: false, // whether or not to hide other sidebar content

      // To avoid search index collision
      // between multiple websites under the same domain
      namespace: 'website-1',

      // Use different indexes for path prefixes (namespaces).
      // NOTE: Only works in 'auto' mode.
      //
      // When initialiazing an index, we look for the first path from the sidebar.
      // If it matches the prefix from the list, we switch to the corresponding index.
      pathNamespaces: ['/zh-cn', '/ru-ru', '/ru-ru/v1'],

      // You can provide a regexp to match prefixes. In this case,
      // the matching substring will be used to identify the index
      pathNamespaces: /^(\/(zh-cn|ru-ru))?(\/(v1|v2))?/
    }
  }
</script>
<script src="//cdn.jsdelivr.net/npm/docsify/lib/docsify.min.js"></script>
<script src="//cdn.jsdelivr.net/npm/docsify/lib/plugins/search.min.js"></script>
```

#2 Google Analytics

Install the plugin and configure the track id.

```html
<script>
  window.$docsify = {
    ga: 'UA-XXXXX-Y'
  }
</script>
<script src="//cdn.jsdelivr.net/npm/docsify/lib/docsify.min.js"></script>
<script src="//cdn.jsdelivr.net/npm/docsify/lib/plugins/ga.min.js"></script>
```

Configure by `data-ga`.

```html
<script src="//cdn.jsdelivr.net/npm/docsify/lib/docsify.min.js" data-ga="UA-XXXXX-Y"></script>
<script src="//cdn.jsdelivr.net/npm/docsify/lib/plugins/ga.min.js"></script>
```

#2 emoji

The default is to support parsing emoji. For example `:100:` will be parsed to :100:. But it is not precise because there is no matching non-emoji string. If you need to correctly parse the emoji string, you need install this plugin.

```html
<script src="//cdn.jsdelivr.net/npm/docsify/lib/plugins/emoji.min.js"></script>
```

?> If you don't want to parse to emoji, you can use __colon_<span>_</span> or `&#58;`. If you need to use in the title, we recommend using `&#58;`. For example, `&#58;100:`

#2 External Script

If the script on the page is an external one (imports a js file via `src` attribute), you'll need this plugin to make it work.

```html
<script src="//cdn.jsdelivr.net/npm/docsify/lib/plugins/external-script.min.js"></script>
```

#2 Zoom image

Medium's image zoom. Based on [medium-zoom](https://github.com/francoischalifour/medium-zoom).

```html
<script src="//cdn.jsdelivr.net/npm/docsify/lib/plugins/zoom-image.min.js"></script>
```

Exclude the special image

```markdown
![](image.png ":no-zoom")
```

#2 Edit on github

Add `Edit on github` button on every pages. Provided by [@njleonzhang](https://github.com/njleonzhang), check [document](https://github.com/njleonzhang/docsify-edit-on-github)

#2 Demo code with instant preview and jsfiddle integration

With this plugin, sample code can be rendered on the page instantly, so that the readers can see the preview immediately.
When readers expand the demo box, the source code and description are shown there. if they click the button `Try in Jsfiddle`,
`jsfiddle.net` will be open with the code of this sample, which allow readers to revise the code and try on their own.

[Vue](https://njleonzhang.github.io/docsify-demo-box-vue/) and [React](https://njleonzhang.github.io/docsify-demo-box-react/) are both supported.

#2 Copy to Clipboard

Add a simple `Click to copy` button to all preformatted code blocks to effortlessly allow users to copy example code from your docs. Provided by [@jperasmus](https://github.com/jperasmus)

```html
<script src="//cdn.jsdelivr.net/npm/docsify-copy-code"></script>
```

See [here](https://github.com/jperasmus/docsify-copy-code/blob/master/README.md) for more details.

#2 Disqus

Disqus comments. https://disqus.com/

```html
<script>
  window.$docsify = {
    disqus: 'shortname'
  }
</script>
<script src="//cdn.jsdelivr.net/npm/docsify/lib/plugins/disqus.min.js"></script>
```

#2 Gitalk

[Gitalk](https://github.com/gitalk/gitalk) is a modern comment component based on Github Issue and Preact.

```html
<link rel="stylesheet" href="//cdn.jsdelivr.net/npm/gitalk/dist/gitalk.css">

<script src="//cdn.jsdelivr.net/npm/docsify/lib/plugins/gitalk.min.js"></script>
<script src="//cdn.jsdelivr.net/npm/gitalk/dist/gitalk.min.js"></script>
<script>
  const gitalk = new Gitalk({
    clientID: 'Github Application Client ID',
    clientSecret: 'Github Application Client Secret',
    repo: 'Github repo',
    owner: 'Github repo owner',
    admin: ['Github repo collaborators, only these guys can initialize github issues'],
    // facebook-like distraction free mode
    distractionFreeMode: false
  })
</script>
```

#2 Pagination

Pagination for docsify. By [@imyelo](https://github.com/imyelo)

```html
<script src="//cdn.jsdelivr.net/npm/docsify/lib/docsify.min.js"></script>
<script src="//cdn.jsdelivr.net/npm/docsify-pagination/dist/docsify-pagination.min.js"></script>
```

#2 Tabs

A docsify.js plugin for displaying tabbed content from markdown.

- [Documentation & Demos](https://jhildenbiddle.github.io/docsify-tabs)

Provided by [@jhildenbiddle](https://github.com/jhildenbiddle/docsify-tabs).

#2 More plugins

See [awesome-docsify](awesome?id=plugins)
