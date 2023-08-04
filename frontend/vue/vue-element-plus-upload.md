# Vue Element Plus Upload

```javascript
function onUpload(opt) {
    let formData = new FormData()
    formData.append('file', opt.file)
    $axios.post('#', formData, {
        headers: {
            'Content-Type': 'multipart/form-data'
        },
        onUploadProgress: function (pe) {
            pe.percent = (pe.loaded / (pe.total / 0.99) * 100).toFixed(0)
            opt.onProgress(pe)
        }
    }).then((res) => {
        opt.onSuccess(res)
    }).catch((err) => {
        opt.onError(err)
    })
}
```

## References

{% embed url="https://juejin.cn/post/7125260228915888142" %}
