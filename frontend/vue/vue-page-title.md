# Vue Page Title

## Method 1: Modifying the `public/index.html` and hard code the title

## Method 2: Using pages field in vue.config.js

```javascript
pages: {
    index: {
      // entry for the page
      entry: 'src/index/main.js',
      // the source template
      template: 'public/index.html',
      // output as dist/index.html
      filename: 'index.html',
      // when using title option,
      // template title tag needs to be <title><%= htmlWebpackPlugin.options.title %></title>
      title: 'Index Page',
      // chunks to include on this page, by default includes
      // extracted common chunks and vendor chunks.
      chunks: ['chunk-vendors', 'chunk-common', 'index']
    },
    // when using the entry-only string format,
    // template is inferred to be `public/subpage.html`
    // and falls back to `public/index.html` if not found.
    // Output filename is inferred to be `subpage.html`.
    subpage: 'src/subpage/main.js'
  }
}
```

## Method 3: Modify title in lifecycle hooks using JavaScript

<pre class="language-javascript"><code class="lang-javascript">&#x3C;script setup>
<strong>onMounted(() => {
</strong><strong>    document.title = 'new title'
</strong>}
&#x3C;/script>
</code></pre>

## Reference

{% embed url="https://stackoverflow.com/questions/62023604/where-to-find-or-how-to-set-htmlwebpackplugin-options-title-in-project-created-w" %}
