<template>
  <div class="pb-3">
    <filter-label label="Quantity"></filter-label>
    <div class="pt-5 flex">
      <div class="inline w-full flex place-content-center border rounded-full py-2 px-2">
        <div class="flex items-center justify-center gap-x-1">
          <button class="px-4 py-2"
                  @click="decreaseCounter">-
          </button>
          {{ count }}
          <button class="px-4 py-2"
                  @click="increaseCounter">+
          </button>
        </div>
      </div>
      <button class="inline flex text-xl justify-center items-center w-full py-3 px-5 m-3 ml-0 text-white rounded-full md:ml-3 bg-primary"
              @click="alertCard(count)"> Submit</button>
    </div>
  </div>
</template>

<script>
import FilterLabel from "./FilterLabel.vue";
export default {
  components: {FilterLabel},
  props: ['alertCard'],
  data: () => ({
    count: 0
  }),
  methods: {
    increaseCounter() {
      this.count++
    },
    decreaseCounter() {
      this.count--
    },
  }
}
</script>

<style scoped>


.bg-primary{
  background-color: navy;
}
</style>