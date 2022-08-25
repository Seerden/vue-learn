## Syntax for (custom) event emits between parent and child components.

-  Parent

   ```
   <script setup lang="ts">
   const addedItems = ref<number[]>([]);
   </script>

   <template>
      <Child @add={(item) => addedItems.push(item)}
   </template>
   ```

-  Child

```
   <script setup lang="ts">
   defineEmits(['add']);
   </script>

   <template>
      <button @click="$emit('add', item)">Add item</button>
   </template>
```
