# Vue Redirect Request (Proxy)

Modify `vue.config.js`

```javascript
const { defineConfig } = require('@vue/cli-service')

module.exports = defineConfig({
devServer: {
    proxy: {
      '/api': {
        target: 'http://127.0.0.1:5000',
        changeOrigin: true
      }
    }
  },
})
```

{% embed url="https://blog.csdn.net/web_noob/article/details/113650896" %}

{% embed url="https://stackoverflow.com/questions/73179887/proxy-error-could-not-proxy-request-users-from-localhost3000-to-http-localh" %}
