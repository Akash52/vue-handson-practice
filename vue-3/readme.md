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

- {{}} is known as mustache tag
- Reactivity is a programming paradigm that allows us to adjust to changes in a declarative manner.

```html
  <body>
    <div id="vue_app">
      <h1 :key="city">{{city}}</h1>
      <p>{{street}}</p>
      <p>{{nation}}</p>

      <p>{{$data}}</p>
    </div>
    <script src="https://unpkg.com/vue@3"></script>
    <script>
      let app = Vue.createApp({
        setup() {
          return {
            street: 'Ngong Road',
          };
        },
        data() {
          return {
            city: 'Nairobi',
            nation: 'Kenya',
          };
        },
      });
      let vue_app = app.mount('#vue_app');
    </script>
  </body>
</html>
```

- v-bind is used to bind data to a DOM element
- v-bind Controlling Attribute Values

```html
<div id="vue_app">
  <h1 :key="city">{{city}}</h1>
  <p>{{street}}</p>
  <p>{{nation}}</p>
  <p>{{$data}}</p>
  <input type="text" :disabled="isDisabled" />
  {{city}}
</div>

<body>
  <script src="https://unpkg.com/vue@3"></script>
  <script>
    let app = Vue.createApp({
      setup() {
        return {
          street: 'Ngong Road',
        };
      },
      data() {
        return {
          city: 'Nairobi',
          nation: 'Kenya',
          isDisabled: true,
        };
      },
    });
    let vue_app = app.mount('#vue_app');
  </script>
</body>
```

```html
<body>
  <div id="vue_app">
    <h1 v-bind:city="city.toUpperCase()">{{nation}}</h1>

    <p>{{nation}}</p>

    <input type="text" v-model="city" :disabled="!false" />

    {{city}}
  </div>

  <script src="https://unpkg.com/vue@3"></script>
  <script>
    let app = Vue.createApp({
      data() {
        return {
          city: 'Nairobi',
          nation: 'Kenya',
        };
      },
    });
    let vue_app = app.mount('#vue_app');
  </script>
</body>
```

- Setup function is another way to set up data and methods.

- 7. Event Modifiers .once, .stop, .self, .capture, and .prevent

- We have six type of event modifer
- once means event monitor once
- stop, .self, .capture is for dealing propogation
- Prevent is disabling default behavior
- Passive Oposite of Prvent

Note -

- clicking the inner div called outer div called Propagation.
  for stoping we use stop modifier
