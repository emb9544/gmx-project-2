<template>
  <filter-label label="Color Options" ></filter-label>
  <div class="grid grid-cols-3  xs:w-2/3 sm:w-1/2 xl:w-full">
    <div v-for="color in colors" :key="color"
         @click="addColorAttributes(color)">
      <div class="relative w-20 mb-6">
        <button
            class="flex items-center justify-center h-20 border-2 rounded-full focus:outline-none"
            @click="activeButton = color.name"
            @mouseover="selectedColor(color.name)"
            @mouseleave="itemName = null"
            :class="{ active: activeButton === color.name }">
          <img
              class="max-w-full max-h-full p-2 mx-auto my-auto cursor-pointer min-h-1/3 min-w-1/2 rounded-3xl"
              :src="color.image"/>
        </button>
        <div class="absolute w-32 text-xs text-center capitalize colorName whitespace-nowrap"
             v-show="itemName == color.name">
          {{ color.name }}
        </div>
      </div>
    </div>
  </div>
</template>
<script>

import FilterLabel from "./FilterLabel.vue"
export default {
  name: "color-options-card",
  components: {FilterLabel},
  props: ['colors', 'addColorAttributes', 'options'],
  methods: {
    selectedColor(color) {
      this.itemName = color
    }
  },
  data() {
    return {
      hover: false,
      activeButton: '',
      itemName: null,
    }
  }

}


</script>

<style scoped>
.colorName {
  margin-left: -24px;
  transition: opacity .25s ease;
}
.rounded-3xl {
  border-radius: 1.5rem;
}
.active {
  filter: drop-shadow(0 10px 8px rgb(0 0 0 / 0.1)) drop-shadow(0 4px 3px rgb(0 0 0 / 0.1));
  border-color: #193c64;
  border-width: 1px;
  top: 1px;
  background-color: white;
  transform: translateY(-10%)
}
</style>