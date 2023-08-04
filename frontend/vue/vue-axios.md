# Vue Axios

## Vue3

### Provide

```javascript
import axios from "axios"

axios.defaults.baseURL = 'https://example.com';

const app = createApp(App)
app.provide('$axios', axios)
```

### Inject

```javascript
<script setup>
import {inject} from 'vue'

const $axios = inject('$axios')
</script>
```
