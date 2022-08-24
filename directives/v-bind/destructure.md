Similar to destructuring component props in JSX

```js
<Task {...task} />
```

we can use `v-bind` to bind (and destructure) all object props, like

```js
<Task v-for="task in tasks" v-bind="task" />
```
