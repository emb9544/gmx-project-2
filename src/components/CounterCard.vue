<template>
  <div class="pb-3 ">
    <filter-label label="Quantity"></filter-label>
    <div class="pt-5 inline w-2/5">
      <div class="flex place-content-center border rounded-2xl w-40 py-2 px-2 ">
        <div class="flex items-center justify-center gap-x-1">
          <button class="px-2 py-2"
                  @click="decreaseCounter">-
          </button>
          {{ count }}
          <button class="px-4 py-2"
                  @click="increaseCounter">+
          </button>
        </div>
      </div>
      <div class="pt-5 inline w-2/5">
        <button class=" flex justify-center items-center w-full py-3 m-3 ml-0 text-white rounded-full md:ml-3 bg-primary"
                @click="alertCard(count)"> Submit</button>
      </div>
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
/*.qy{
  justify-content: center;
  align-items: center;
  display: flex;
  height: 100%;
  text-align: center;

}*/
button {
  width: 45px;
  height: 40px;
  font-size: 20px;
}
.bg-primary{
  background-color: navy;
  width: 40%;
}

</style>