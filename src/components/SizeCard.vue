<template>
  <div class="py-5">
    <filter-label label="Sizes" class="pb-3"></filter-label>
    <div class="flex border-2 rounded-full border-light w-fc">
      <div>
        <button
            class="px-3 py-3 uppercase cursor-pointer last:border-r-0 last:rounded-r-full first:rounded-l-full border-light"
            v-for="size in sizes"
            :key="size"
            @click="updateAttributes('13', size.id)">
          <h3>{{ getSizeName(size)}}</h3>
        </button>
      </div>
    </div>
  </div>
</template>

<script>
import FilterLabel from "./FilterLabel.vue";
export default {
  name: "size-card",
  components: {FilterLabel},
  props: ['sizes', 'updateAttributes'],

  methods: {
    getSizeName(size) {
      const keys = {
        '3X-Large':'3XL',
        '2X-Large':'2XL',
        'X-Large':'XL',
        'Large':'L',
        'Medium':'M',
        'Small':'S',
        'X-Small':'XS'
      }
      return keys[size.name];
    }
  }

}
</script>

<style scoped>
button:focus {
  background-color: navy;
  border-radius: 9999px;
  color: white;
}
.w-fc {
  width: fit-content;
}


</style>