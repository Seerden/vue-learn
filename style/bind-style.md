## References

See [Vue docs: Class and Style
Bindings](https://vuejs.org/guide/essentials/class-and-style.html)

## Info

-  `v-bind:class` or `:class` can be used to dynamically toggle classes. Note
   that `class` and `:class` can co-exist.

   ```js
   <div class="round" :class="{ active: isActive }"></div>
   ```

   -  Also note that the bound object doesn't have to be inline (it can be a
      reactive, or ref (I guess) as well that we then reference inside `:class`.

-  We can also bind styles, either inline or through a combination of `script` and
   (scoped) `style` tags.

   ```js
   <script setup>
   import { ref } from "vue";

   const color = ref("red");
   </script>

   <template>
      <button @click="color = color === 'red' ? 'green' : 'red'">
         My color is {{ color }}
      </button>
   </template>

   <style scoped>
   button {
      color: v-bind(color);
   }
   </style>
   ```
