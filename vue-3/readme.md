### Proxy

- Proxy is built in Constructor

### Reflect

- Reflect is built in Object

```html
<body>
  <script src="https://unpkg.com/vue@3"></script>
  <script>
    let data = {
      message: 'Hello Vue!',
    };
    //Reflact
    function test() {
      console.log(this);
    }
    // test.apply(data);
    Reflect.apply(test, data, []);
  </script>
</body>
```
