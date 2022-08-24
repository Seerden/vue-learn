# References

-  component props: [Vue docs: Typing Component Props](https://vuejs.org/guide/typescript/composition-api.html#typing-component-props)

# Component props

We define props like

```js
<script setup lang="ts">
interface Props {
  foo: string
  bar?: number
}

const props = defineProps<Props>()
</script>
```

## Limitations

The type of `T` in `defineProps<T>` has to be either an object literal type, or
a reference to a type that's declared _in the same file_.

> The interface or object literal type can contain references to types imported
> from other files, however, the generic argument itself passed to defineProps
> cannot be an imported type

Note that we can use (experimental) vite plugin
`vite-plugin-vue-type-imports` to get around this, and be
able to import types and use them in the defineProps generic argument.
